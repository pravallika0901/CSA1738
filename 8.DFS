def dfs_recursive(graph, start, visited=None):
    if visited is None:
        visited = set()
    visited.add(start)
    print(start, end=' ')  # Print the node as it's visited

    for neighbor in graph[start]:
        if neighbor not in visited:
            dfs_recursive(graph, neighbor, visited)

def dfs_iterative(graph, start):
    visited = set()
    stack = [start]
    dfs_order = []

    while stack:
        node = stack.pop()
        if node not in visited:
            visited.add(node)
            dfs_order.append(node)
            stack.extend(reversed(graph[node]))  # Add neighbors in reverse order to visit them in the correct order
    
    return dfs_order

# Example usage
if __name__ == "__main__":
    graph = {
        'A': ['B', 'C'],
        'B': ['A', 'D', 'E'],
        'C': ['A', 'F'],
        'D': ['B'],
        'E': ['B', 'F'],
        'F': ['C', 'E']
    }
    
    start_node = 'A'
    print(f"DFS (recursive) starting from node {start_node}: ", end='')
    dfs_recursive(graph, start_node)
    print()  # For newline

    dfs_result = dfs_iterative(graph, start_node)
    print(f"DFS (iterative) starting from node {start_node}: {dfs_result}")
