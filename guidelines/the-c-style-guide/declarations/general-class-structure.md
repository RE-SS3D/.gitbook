# General class structure

A class must respect the following order, from top to bottom

* Events and delegates declaration.
* Private enums declaration.
* Private internal classes.
* Member variables.
* Properties.
* Methods.

**BAD:**

```
 public sealed class Container : NetworkActor
    {
        public event ContainerContentsHandler OnContentsChanged;

        public Vector2Int Size;
        public AttachedContainer AttachedTo { get; set; }
        
        [SyncObject]
        private readonly SyncList<StoredItem> _storedItems = new();
        
        private readonly object _modificationLock = new();
        
        public float LastModification { get; private set; }
        
        public delegate void ContainerContentsHandler(Container container, IEnumerable<Item> oldItems,IEnumerable<Item> newItems, ContainerChangeType type);

        ...
```

**GOOD:**

```
 public sealed class Container : NetworkActor
    {
        public event ContainerContentsHandler OnContentsChanged;
        public delegate void ContainerContentsHandler(Container container, IEnumerable<Item> oldItems,IEnumerable<Item> newItems, ContainerChangeType type);
  
        public Vector2Int Size; 
        private readonly object _modificationLock = new();
        
        [SyncObject]
        private readonly SyncList<StoredItem> _storedItems = new();
        
        public AttachedContainer AttachedTo { get; set; }
        public float LastModification { get; private set; }
   

        ...
```

