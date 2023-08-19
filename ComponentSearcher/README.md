# ComponentSearcher<T> Documentation

## Summary

The `ComponentSearcher<T>` script is a versatile tool designed for locating components of type `T` within Unity, as well as performing various operations on these components, such as finding the closest, furthest, or components within a specific radius.

## Usage

This script is a generic class that can be utilized in any Unity project.

### Example Usage

```csharp
using System.Collections.Generic;
using UnityEngine;

public class ExampleUsage : MonoBehaviour
{
    private List<MyComponentType> components;

    private void Start()
    {
        // Populate the 'components' list with your MyComponentType components
    }

    private void Update()
    {
        Vector3 currentPosition = transform.position;

        MyComponentType closestComponent = ComponentSearcher<MyComponentType>.Closest(currentPosition, components);
        MyComponentType furthestComponent = ComponentSearcher<MyComponentType>.Furthest(currentPosition, components);

        float searchRadius = 10f;
        List<MyComponentType> componentsInRange = new List<MyComponentType>();
        ComponentSearcher<MyComponentType>.InRadius(currentPosition, searchRadius, out componentsInRange);

        // Now you can interact with the found components
    }
}
```
## Methods
### `Closest(Vector3 pos, List<T> components) : T`
Returns the closest component of type `T` to the given position `pos` from the `components` list.

### `Closest(Vector3 pos, float radius) : T`
Returns the closest component of type `T` to the given position `pos` within the specified `radius`.

### `Furthest(Vector3 pos, List<T> components) : T`
Returns the furthest component of type `T` from the given position `pos` within the `components` list.

### `Furthest(Vector3 pos, float radius) : T`
Returns the furthest component of type `T` from the given position `pos` within the specified `radius`.

### `InRadius(Vector3 pos, float radius, out List<T> results, bool findOnlyEnabled = true) : int`
Finds all components of type `T` located within the `radius` from the given position `pos`. Results are stored in the `results` list. By default, the search is limited to only enabled components.

## Notes
* Make sure your `MyComponentType` type inherits from `Component`.
* Properly include the necessary `using` directives to use the script.
