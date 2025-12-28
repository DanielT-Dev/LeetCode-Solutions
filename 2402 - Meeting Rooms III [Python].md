# Problem Statement: [https://leetcode.com/problems/meeting-rooms-iii/description/?envType=daily-question&envId=2025-12-27](https://leetcode.com/problems/meeting-rooms-iii/description/?envType=daily-question&envId=2025-12-27)
# My Solution: 
```python
class Solution:
    def mostBooked(self, n: int, meetings: List[List[int]]) -> int:
        
        rooms = [0] * n
        freq = [0] * n
        pq = [(0, i) for i in range(n)]
        free_rooms = []
        max_freq = time = 0
        result = float("inf")

        # Sort in increasing order by start time
        meetings.sort(key= lambda x: (x[0]))

        for meeting in meetings:

            time = meeting[0]
            end = meeting[1]
            room_index = -1
            finish_time = 0

            # Find first open room
            while pq and pq[0][0] <= time:
                _, r = heapq.heappop(pq)
                heapq.heappush(free_rooms, r)
            
            if free_rooms:
                room_index = heapq.heappop(free_rooms)
                finish_time = end
            else:
                room_time, room_index = heapq.heappop(pq)
                finish_time = room_time + (end - time)

            # Close room
            rooms[room_index] = finish_time
            # Count meetings
            freq[room_index] += 1
            # Add future room
            heapq.heappush(pq, (finish_time, room_index))

            # Update result
            if freq[room_index] > max_freq:
                max_freq = freq[room_index]
                result = room_index
            elif freq[room_index] == max_freq:
                result = min(result, room_index)

        return result
```
