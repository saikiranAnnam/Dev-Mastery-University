# Operations of Array

```python
class Array: 
    def __init__(self, capacity):
        self.capacity = capacity
        self.size = 0
        self.data = [None] * capacity
    
    def __len__(self):
        return self.size
    
    # check if the array is empty
    def is_empty(self):
        return self.size == 0
    
    # return the item at the index and blows up if out of bound
    def at(self, index):
        if index < 0 or index >= self.size: 
            raise IndexError("Index out of bounds")
        return self.data[index]
    
    # insert the element in the back of the array 
    def push(self, item):
        if self.size == self.capacity:
            return False
        self.data[self.size] = item
        self.size += 1
        return True
    
    # insert the element at a postion or specific index
    def insert(self, item, index):
        if index < 0 or index > self.size or self.size == self.capacity:
            return False
        for i in range(self.size, index, -1):
            self.data[i] = self.data[i - 1]
        self.data[index] = item
        self.size +=1 
        return True
    
    # insert the element at the front
    def prepend(self, item):
        return self.insert(0, item)
    
    # remove form end and return value 
    def pop(self):
        if self.size == 0:
            raise IndexError("Pop from empty array")
        
        val = self.data[self.size - 1]
        self.data[self.size - 1] = None
        self.size -= 1
        return val
    
    # delete the element in the specific position
    def delete(self, index):
        if index < 0 or index >= self.size:
            return False
        for i in range(index, self.size - 1):
            self.data[i] = self.data[i+1]
        self.data[self.size - 1] = None
        self.size -= 1
        return True
    
    # looks for value and removes index holding it (even if in multiple places)
    def remove(self, item):
        write = 0
        removed = 0
        for read in range(self.size):
            if self.data[read] == item:
                removed += 1
            else:
                self.data[write] = self.data[read]
                write += 1
        for i in range(write, self.size):
            self.data[i] = None
        self.size = write
        return removed

    # looks for value and returns first index with that value, -1 if not found
    def find(self, item):
        for i in range(self.size):
            if self.data[i] == item:
                return i
        return -1
```

