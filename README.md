# task-4
rows = int(input("Enter the number of rows: "))
cols = int(input("Enter the number of columns: "))
print("Enter the elements of the matrix (0s and 1s, separated by space):")
matrix = [input().split() for _ in range(rows)]
x = int(input("Enter the x-coordinate of the target pixel: "))
y = int(input("Enter the y-coordinate of the target pixel: "))
stack = [(0, 0)]
while stack:
    curr_x, curr_y = stack.pop()
    if (curr_x, curr_y) == (x, y):
        print("Path found")
        break
    for dx, dy in [(1, 0), (-1, 0), (0, 1), (0, -1)]:
        new_x, new_y = curr_x + dx, curr_y + dy
        if 0 <= new_x < rows and 0 <= new_y < cols and matrix[new_x][new_y] == '1':
            stack.append((new_x, new_y))
else:
         print("Path not found")
