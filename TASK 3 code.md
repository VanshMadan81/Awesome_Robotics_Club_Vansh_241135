code in python:
grid = [
    ['S','.','.','.','.','~','.','.','^','.'],
    ['#','#','#','.','.','~','#','.','^','.'],
    ['.','.','.','#','.','.','#','.','.','.'],
    ['.','~','~','#','.','.','.','.','.','.'],
    ['.','.','.','.','.','#','#','#','#','.'],
    ['^','^','.','.','.','.','.','.','~','.'],
    ['#','.','.','.','.','#','~','~','~','.'],
    ['.','.','#','#','.','.','.','.','.','.'],
    ['.','.','.','.','.','^','^','^','^','G'],
    ['.','#','#','#','#','#','#','.','.','.']
]
current = (0, 0)
path = [current]
total_cost = 0
#we will go in the drections by this priority order:right, down, left, up
directions = [(0, 1), (1, 0), (0, -1), (-1, 0)] 

while current != (8, 9):
    min_cost = float('inf')
    candidates = []
    
    # Checking all directions in the priority order
    for xo, yo in directions:
        xn, yn = current[0] + xo, current[1] + yo
        
        if 0 <= xn < 10 and 0 <= yn < 10:
            cell = grid[xn][yn]
            if cell == '#':
                continue
            if cell in ('.', 'S', 'G'):
                cost = 1
            elif cell == '~':
                cost = 3
            elif cell == '^':
                cost = 5
            
            # Update candidates
            if cost < min_cost:
                min_cost = cost
                candidates = [(xn, yn)]
            elif cost == min_cost:
                candidates.append((xn, yn))
    
    if not candidates:
        print("No valid path exists!")
        break
    
    # Select next position based on priority
    next_pos = candidates[0]
    total_cost += min_cost
    path.append(next_pos)
    current = next_pos

# Final results
print("Path coordinates:")
for coord in path:
    print(coord)
print("Total cost:",total_cost)
