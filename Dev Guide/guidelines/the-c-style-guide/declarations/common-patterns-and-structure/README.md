# Common Patterns and Structure

This section includes some rules of thumb for design patterns and code structure

#### Error handling

**Avoid** throwing <mark style="color:blue;">**exceptions**</mark>. Instead **log** and **error**. <mark style="color:green;">**Methods**</mark> returning <mark style="color:blue;">**values**</mark> should <mark style="color:blue;">**return null**</mark> in addition to **logging** an <mark style="color:blue;">**error**</mark>

**BAD:**

```
public List<Transform> FindAThing(int arg){
    ...
    if (notFound) {
        throw new NotFoundException();
    }
}
```

**GOOD:**

```
public List<Transform> FindAThing(int arg){
    ...
    if (notFound) {
        Debug.LogError("Thing not found");
        return null;
    }
}
```

#### Finding references

Don't use <mark style="color:green;">**Find**</mark> or in other ways refer to <mark style="color:purple;">**GameObjects**</mark> by <mark style="color:blue;">**name**</mark> or <mark style="color:blue;">**child index**</mark> _when possible_. **Reference by reference** is less error prone and more flexible. Expect people to set the <mark style="color:blue;">**fields**</mark> in the inspector and log warnings if they don't.

**BAD:**

```
private GameObject _someMember;

private void Start() {
    _someMember = GameObject.Find("ObjectName");
}
```

#### RequireComponent

Prefer <mark style="color:green;">**RequireComponent**</mark> and <mark style="color:green;">**GetComponent**</mark> over <mark style="color:green;">**AddComponent**</mark>. Having the <mark style="color:purple;">**components**</mark> in the inspector let's us edit them. <mark style="color:green;">**AddComponent**</mark> limits us.

**BAD:**

```
public class : MonoBehaviour
{
    private AudioSource _audioSource;

    private void Start() {
        _audioSource = gameObject.AddCompenent<AudioSource>();
    }
}
```

**GOOD:**

```
[RequireComponent(typeof(AudioSource))]
public class : MonoBehaviour
{
    private AudioSource _audioSource;

    private void Start() {
        _audioSource = GetCompenent<AudioSource>();
    }
}
```

#### Properties with backing fields

<mark style="color:blue;">**Properties**</mark> can be used for access control to <mark style="color:blue;">**fields**</mark>, and when using <mark style="color:blue;">**backing fields**</mark> they can be <mark style="color:blue;">**private**</mark> and let us change them in the inspector. Consider when a <mark style="color:blue;">**fields**</mark> should be <mark style="color:blue;">**public**</mark> and prefer <mark style="color:blue;">**properties with backing fields**</mark>.

Sometimes it's just nice to see them for debugging, even if we don't change them, so consider making more of your private fields visible.

**OKAY:**

```
public GameObject SomeMember;
```

**BETTER:**

```
[SerializeField] private GameObject _someMember;
public GameObject SomeMember => _someMember;
```
