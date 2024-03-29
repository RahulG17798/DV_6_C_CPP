# Generic Lists

Generic lists implementation has 3 parts
* Generic List
* Generic List Iterator
* Driver program

Generic lists can contain any copyable data and resize dynamically.  
Generic lists maintain data in the form of void*.  
Data should be copyable and addressable value i.e. a lvalue.  
Data returned from Generic list is a void* which has to be converted to original data type.

A generic list iterator is also provide which work as a pointer.
Iterator can be moved only in forward direction.

### GList
``` c
typedef struct GList {
    void *data;
    struct GList *next;
} GList_t;
```

### GIter
``` c
typedef struct GIter {
    struct GList *gnode;
} GIter_t;
```

## API supported
### _create generic list_
``` c
GList_t new_gList();
```
Creates a new generic list object

### _delete generic list_
``` c
void free_gList(GList_t);
```
Frees generic list object and all of its contents

### _get value at index_
``` c
void* gList_at(GList_t, size_t);
```
Get value at an index

### _insert value at index_
``` c
void gList_insert(data, size);
```
Insert data in generic list. -1 index refers to end.

### _create generic list iterator_
``` c
GIter_t new_gIter();
```
Create a generic list iterator

### _delete generic list iterator_
``` c
void free_gIter(GIter_t);
```
Remove generic list iterator

### _move generic list iterator forward_
``` c
void gIter_next(GIter_t *);
```
Move generic list iterator forward

### _check if generic list iterator points to NULL_
``` c
int gIter_IsNull(GIter_t);
```
Check if generic list iterator points to a NULL location

### _get value from generic list iterator_
``` c
void* gIter_value(GIter_t);
```
Get value from a generic list iterator