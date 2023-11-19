# SS3D's coder good practices

<mark style="color:purple;">This is a draft to remind us we have to write this little guide.</mark>

* Avoid using Debug.Log, use Punpun logger instead. This is because we get much more relevant data using Punpun compared to Debug.Log.
* Use SystemLocator instead of the Find method from Unity when trying to get a reference. This is less prone to break and more efficient.
* To get an input, don't use Unity's built in methods, use instead our input system (put link there)
