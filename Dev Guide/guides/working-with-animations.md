# Working with animations

You might wonder how to trigger an effect during an animation, how to call functions when an animation ends, even better, have your effect still trigger at the right time even if you change your animation. The answer is **state machine behaviours.**

{% embed url="https://docs.unity3d.com/Manual/StateMachineBehaviours.html" %}

To make it simple, SMBs are scripts you're going to put on states in animator controller. It calls some callback methods when entering and leaving a state.

In this page, I'll provide an example on how to set up properly an airlock, using it.



## Airlock example

Say you want some lights on your airlock to turn green when opening, red when closing and black when idle.

We have the following state machine for the airlock.



<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption><p>State machine of the airlock and its four states</p></figcaption></figure>

During the opening state, the animator play the "opening" animation.

During the closingstate, the animator play the "closing" animation.

When selecting a state, see the "Add behaviour" option. We're going to use that to write a script to handle the airlock lights.



<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption><p>The inspector for the opening state</p></figcaption></figure>

As said earlier, SMB's have callbacks when entering and leaving a state.

We're going to use two of them here, OnStateExit and OnStateEnter.

`public override void OnStateExit(Animator animator, AnimatorStateInfo stateInfo, int layerIndex)`

`public override void OnStateEnter(Animator animator, AnimatorStateInfo stateInfo, int layerIndex)`

The idea is simple : let's put our behaviour on the two states, opening and closing. When leaving a state, we know that the door is idle, so we're just going to make that call (we'll detail the ChangeColors method later).

```
    public override void OnStateExit(Animator animator, AnimatorStateInfo stateInfo, int layerIndex)
    {
        ChangeColors(_idleColor, animator, stateInfo, layerIndex);
    }
```

Since we want to use the same script both when closing and opening the door (notice we could write two different scripts for simpler logic but harder management of files), when entering a state, we need to check in which state we're going.

Pretty simple, the code is self explanatory, we're using the data from the AnimatorStateInfo to retrieve the data we need :&#x20;

```
/ublic override void OnStateEnter(Animator animator, AnimatorStateInfo stateInfo, int layerIndex)
{
    if (stateInfo.IsName(Opening))
    {
        ChangeColors(_openingColor, animator, stateInfo, layerIndex);
    }
    if (stateInfo.IsName(Closing))
    {
        ChangeColors(_closingColor, animator, stateInfo, layerIndex);
    }
}
```

Now, let's see what's going on in the ChangeColors method.

Contrary to a classic monobehaviour, we can't define serialised field on a SMB, so if we need

to access stuff on our game object we need a simple trick. The callback from the SMB are sending back our animator component, so we have an easy reference to the game object the animator is onto. We can use that game object reference to access just any script we need, on our game object.

Here we use that to retrieve mesh renderers and skinned mesh renderers, that we put into lists on the AirlockOpener script.

Once we have them, we can do whatever we want with them, here we just modify some material colors and we modify some blend shape.

```csharp
       
    private void ChangeColors(Color color, Animator animator) 
    { 
         var renderers = animator.GetComponent<AirLockOpener>().MeshesToColor;
         var skinnedRenderers = animator.GetComponent<AirLockOpener>().SkinnedMeshesToColor;
         foreach (var renderer in renderers) 
         { 
             renderer.materials[DOOR_LIGHT_MATERIAL_INDEX].color = color; 
         } 
         
         foreach (var skinnedRenderer in skinnedRenderers)
         {
            if (color == _openingColor)
            {
                skinnedRenderer.SetBlendShapeWeight(1, 100);
                skinnedRenderer.SetBlendShapeWeight(2, 0);
            }
            else if (color == _closingColor)
            {
                skinnedRenderer.SetBlendShapeWeight(1, 0);
                skinnedRenderer.SetBlendShapeWeight(2, 100);
            }
            else
            {
                skinnedRenderer.SetBlendShapeWeight(1, 0);
                skinnedRenderer.SetBlendShapeWeight(2, 0);
            }
         }

    }
```

