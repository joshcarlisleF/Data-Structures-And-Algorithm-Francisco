import heapq

print("Laboratory Activity 1: Min Heap and Max Heap")
print("=" * 50)

values = [35, 20, 15, 40, 50, 10, 25]

# ---------- MIN HEAP ----------
print("\n--- Min Heap ---")
min_heap = []

for num in values:
    heapq.heappush(min_heap, num)
    print(f"After inserting {num}: {min_heap}")

print(f"\nMinimum value: {min_heap[0]}")


# ---------- MAX HEAP ----------
print("\n--- Max Heap ---")
max_heap = []

for num in values:
    # push negative numbers to simulate a max heap
    heapq.heappush(max_heap, -num)
    display = [-x for x in max_heap]
    print(f"After inserting {num}: {display}")

print(f"\nMaximum value: {-max_heap[0]}")


print("\n\nLaboratory Activity 2: Heap Operations and Heapify")
print("=" * 50)

# start with a normal list
heap = [5, 3, 8, 1, 2]
print(f"Initial list: {heap}")

# turn the list into a min heap
heapq.heapify(heap)
print(f"After heapify(): {heap}")

# insert 5
heapq.heappush(heap, 5)
print(f"After inserting 5: {heap}")

# change the inserted value to 8
heap.remove(5)
heapq.heapify(heap)
heapq.heappush(heap, 8)
print(f"After changing to 8: {heap}")

# change the inserted value to 3
heap.remove(8)
heapq.heapify(heap)
heapq.heappush(heap, 3)
print(f"After changing to 3: {heap}")

# peek at the minimum
print(f"\nMinimum element (peek): {heap[0]}")

# extract the minimum
min_val = heapq.heappop(heap)
print(f"Extracted value: {min_val}")
print(f"Heap after extraction: {heap}")

# Note: heapify() rearranges a list so it follows the heap property.
# After calling it, the smallest element is always at index 0
# and every parent is smaller than or equal to its children.
# This lets us insert and extract elements efficiently.
