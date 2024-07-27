% Define edges of the graph with their costs
edge(a, b, 1).
edge(a, c, 3).
edge(b, d, 3).
edge(b, e, 6).
edge(c, e, 2).
edge(d, f, 1).
edge(e, f, 2).

% Define the heuristic values (estimated cost to reach the goal)
heuristic(a, 6).
heuristic(b, 4).
heuristic(c, 5).
heuristic(d, 2).
heuristic(e, 1).
heuristic(f, 0). % Goal node

% Best First Search algorithm
best_first_search(Start, Goal, Path) :-
    heuristic(Start, H),
    bfs([[Start, H]], Goal, [], Path).

% Helper predicate to implement BFS
bfs([[Goal|Path]|_], Goal, _, [Goal|Path]).
bfs([[Current|Path]|Rest], Goal, Visited, FinalPath) :-
    findall([Next, H, Current|Path],
            (edge(Current, Next, _),
             \+ member(Next, Visited),
             heuristic(Next, H)),
            Neighbors),
    append(Rest, Neighbors, NewFrontier),
    sort(2, @=<, NewFrontier, SortedFrontier),
    bfs(SortedFrontier, Goal, [Current|Visited], FinalPath).

% Query to find the path
find_path(Start, Goal, Path) :-
    best_first_search(Start, Goal, RevPath),
    reverse(RevPath, Path).
