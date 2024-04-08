# Number-of-Students-Unable-to-Eat-Lunch
The school cafeteria offers circular and square sandwiches at lunch break, referred to by numbers 0 and 1 respectively. All students stand in a queue. Each student either prefers square or circular sandwiches.  The number of sandwiches in the cafeteria is equal to the number of students. The sandwiches are placed in a stack.

class Solution:
    def countStudents(self, students: List[int], sandwiches: List[int]) -> int:
        counts = [0, 0]
        for student in students:
            counts[student] += 1

        remaining = len(sandwiches)
        for sandwich in sandwiches:
            if counts[sandwich] == 0:
                break
            if remaining == 0:
                break
            counts[sandwich] -= 1
            remaining -= 1
        
        return remaining
