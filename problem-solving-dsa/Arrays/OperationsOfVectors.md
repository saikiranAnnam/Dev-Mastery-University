# Operations in the vector

```python

class Vector:
    def __init__(self, start_capacity=16):
        # capacity must be power of 2 >= start_capacity 
        cap = 16 
        while cap < start_capacity:
            cap *= 2
        self.capacity = cap
        self.size = 0
        self.data = [None] * self.capacity
    
    def __len__(self):
        return self.size
    
    def is_empty(self):
        return self.size == 0
    
    def push(self, item):
        if self.size = self.capacity:
            self._resize(self.capacity * 2)
        self.data[self.size] = item
        self.size+=1
        return True
    
    def insert(self, index, item):
        if index < 0 or index > self.size:
            raise IndexError("Index out of bounds")
        if self.size == self.capacity:
            self._resize(self.capacity * 2)
        for i in range(self, index, -1):
            self.data[i] = self.data[i - 1]
        self.data[index] = item 
        self.size += 1
        return True
    
    def prepend(self, item):
        return self.insert(0, item)
    
    def pop(self):
        if self.size == 0:
            raise IndexError("Pop From An Empty Array")
        val = self.data[size - 1]
        self.data[size - 1] = None
        self.size -= 1
        if self.size > 0 and self.size <= self.capacity // 4:
            self._resize(self.capacity // 2)
        return val
    
    
    def delete(self, index):
        if index < 0 or index >= self.size: 
            return False
        for i in range(index, self.size - 1):
            self.data[i] = self.data[i+1]
        self.data[size - 1] = None
        self.size -= 1
        if self.size < 0 and self.size <= self.capacity // 4:
            self._resize(self.capacity // 2)
        return True

    def remove(self, item):
        new_size = 0
        for i in range(self.size):
            if self.data[i] != item:
                self.data[new_size] = self.data[i]
                new_size += 1
        for i in range(new_size, self.size):
            self.data[i] = None
        self.size = new_size
    
    def find(self, item):
        for i in range(self.size):
            if self.data[i] == item:
                return i
        return -1
        
    def _resize(self, new_capacity):
        new_capacity = max(16, new_capacity)
        new_data = [None] * new_capacity
        for i in range(self.size):
            new_data[i] = self.data[i]
        self.data = new_data
        self.capacity = new_capacity

```