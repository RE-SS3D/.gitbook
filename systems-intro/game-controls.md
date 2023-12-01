# Game Controls

_**For a list of current controls and control ideas see link below.**_

{% content-ref url="broken-reference" %}
[Broken link](broken-reference)
{% endcontent-ref %}

## Input Actions

_**All implemented controls are (and must be) in Content/Systems/Input/Controls.inputactions**_

If you are not familiar with the new input system, here are two [good ](https://docs.unity3d.com/Packages/com.unity.inputsystem@1.0/manual/Actions.html#using-actions)[guides](https://gamedevbeginner.com/input-in-unity-made-easy-complete-guide-to-the-new-system/#action\_maps) for almost everything you might need.

After saving Controls.InputAction, it regenerates Console class in Scripts/SS3D/System/Inputs. You can use Controls class in your script by getting Input property in InputSystem through Subsystems.

All actions and action maps should be named in PascalCase with spaces between words. (Toggle Run, Snap Right, Snap Left, etc). Avoid long names.

All handlers, that subscribe to actions, have to contain InputAction.CallbackContext argument. Handlers have to be subscribed to actions in OnStart() and unsubscribed in OnDestroyed().

If you want to Disable/Enable some acitons (or action maps), use Toggle methods in InputSystem, otherwise, it will  cause issues.

Input Consumption is enabled. It means, in actions with modifiers you have to press modifiers first and binding last. This feature prevent multiple actions from being performed unintentionally (For example, if you have E action and CTRL+E action and you pressed CTRL+E, E action won't be performed).
