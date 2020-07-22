Use python threads and queues together to execute code in parallel (python multithreading, concurrency, and parallelism).

```python
import Queue
import threading

class Worker(threading.Thread):
    def __init__(self, queue):
        threading.Thread.__init__(self)
        self.queue = queue

    def run(self):
        while True:
            task = self.queue.get()
            task.save()
            self.queue.task_done()

NUMBER_OF_THREADS = 100

queue = Queue.Queue()
for i in range(NUMBER_OF_THREADS):
    t = Worker(queue)
    t.daemon = True
    t.start()

for obj in MyModel.objects.all():
    queue.put(obj)

queue.join()
```