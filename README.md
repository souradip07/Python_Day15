# Python_Day15

#Activities: Simulate FIFO and LIFO Mechanisms for Signal Processing
#Simulating a Stack [LIFO (Last In, First Out)] in Python
class Stack:
    def __init__(self):
        self.stack = []
    
    def push(self, item):
        self.stack.append(item)
    
    def pop(self):
        if not self.is_empty():
            return self.stack.pop()
        return None
    
    def peek(self):
        if not self.is_empty():
            return self.stack[-1]
        return None
    
    def is_empty(self):
        return len(self.stack) == 0
    
    def size(self):
        return len(self.stack)

# Example usage:
signal_stack = Stack()
signal_stack.push(1)
signal_stack.push(2)
signal_stack.push(3)
print("Top of the stack:", signal_stack.peek())
print("Popped from stack:", signal_stack.pop())
print("Stack size:", signal_stack.size())


#Simulating a Queue [FIFO (First In, First Out)] in Python
class Queue:
    def __init__(self):
        self.queue = []
    
    def enqueue(self, item):
        self.queue.append(item)
    
    def dequeue(self):
        if not self.is_empty():
            return self.queue.pop(0)
        return None
    
    def peek(self):
        if not self.is_empty():
            return self.queue[0]
        return None
    
    def is_empty(self):
        return len(self.queue) == 0
    
    def size(self):
        return len(self.queue)

# Example usage:
signal_queue = Queue()
signal_queue.enqueue(1)
signal_queue.enqueue(2)
signal_queue.enqueue(3)
print("Front of the queue:", signal_queue.peek())
print("Dequeued from queue:", signal_queue.dequeue())
print("Queue size:", signal_queue.size())


#Project: Build a Queue-Based System for Signal Buffering
#Example Code for Signal Buffering System
class SignalBuffer:
    def __init__(self):
        self.buffer = Queue()
    
    def add_signal(self, signal):
        self.buffer.enqueue(signal)
        print(f"Signal {signal} added to buffer.")
    
    def process_signals(self):
        while not self.buffer.is_empty():
            signal = self.buffer.dequeue()
            self.process_signal(signal)
    
    def process_signal(self, signal):
        # Simulate processing of the signal (e.g., analyze, log, etc.)
        print(f"Processing signal: {signal}")

# Example usage:
signal_buffer = SignalBuffer()
signal_buffer.add_signal(10)
signal_buffer.add_signal(20)
signal_buffer.add_signal(30)
print("Processing signals...")
signal_buffer.process_signals()
