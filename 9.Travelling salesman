import itertools

# Function to calculate the total distance of the route
def total_distance(route, distances):
    total = 0
    for i in range(len(route) - 1):
        total += distances[route[i]][route[i + 1]]
    total += distances[route[-1]][route[0]]  # Return to the starting city
    return total

# Function to find the shortest route using brute force
def tsp_brute_force(distances):
    n = len(distances)
    cities = list(range(n))
    shortest_route = None
    shortest_distance = float('inf')

    # Generate all possible permutations of cities
    for perm in itertools.permutations(cities):
        distance = total_distance(perm, distances)
        if distance < shortest_distance:
            shortest_distance = distance
            shortest_route = perm

    return shortest_route, shortest_distance

# Example distances between cities (replace with your own)
distances = [
    [0, 10, 15, 20],
    [10, 0, 35, 25],
    [15, 35, 0, 30],
    [20, 25, 30, 0]
]

shortest_route, shortest_distance = tsp_brute_force(distances)
print("Shortest Route:", shortest_route)
print("Shortest Distance:", shortest_distance)

