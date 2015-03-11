# When to use blocks, delegates or data source

## Block
- Asynchronous (For example: networking operations)
- User inputs with multiple options (For example: UIAlertView's YES and NO)
- Data source driven inputs (For example: A table items with action blocks that were defined in the data source)
- Returns many values (For example looking for a field in a collection and returning the field and the indexPath)
- If there’s no tracked state or if state it’s defined in the same method

## Delegate
- Synchronous (For example: buttons actions in views that should perform on their parents)
- Shouldn't return values
- Provides control over performing an action (For example: UITextField's shouldEndEditing)
- User input with one action (For example: buttons actions in views that should perform on their parents)
- If tracked state is shared (if state is stored in a property or a constant)

## Data source
- Returns ONE value

# Core Data

## Attribute naming

When crafting data models, use generic wording for ID properties.

Use `remoteID` and `localID` when you are in need of syncing.

**For example:**

```objc
Note *note;
note.localID = 12; // local
note.remoteID = 10; // from backend
```

**Not:**

```objc```
Note *note;
note.noteID = 1;
```

