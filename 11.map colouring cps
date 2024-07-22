class MapColoringCSP:
    def __init__(self, variables, domains, constraints):
        self.variables = variables  # List of variable names (regions)
        self.domains = domains  # Dictionary mapping variables to possible colors
        self.constraints = constraints  # List of constraint functions

    def is_consistent(self, variable, assignment, value):
        for constraint in self.constraints:
            if not constraint(variable, value, assignment):
                return False
        return True

    def backtracking_search(self):
        return self.backtrack({})

    def backtrack(self, assignment):
        if len(assignment) == len(self.variables):
            return assignment

        unassigned = [var for var in self.variables if var not in assignment]
        var = unassigned[0]

        for value in self.domains[var]:
            if self.is_consistent(var, assignment, value):
                assignment[var] = value
                result = self.backtrack(assignment)
                if result:
                    return result
                del assignment[var]
        return None

def not_adjacent_constraint(region1, color1, assignment):
    adjacent_regions = {
        'WA': ['NT', 'SA'],
        'NT': ['WA', 'SA', 'Q'],
        'SA': ['WA', 'NT', 'Q', 'NSW', 'V'],
        'Q': ['NT', 'SA', 'NSW'],
        'NSW': ['Q', 'SA', 'V'],
        'V': ['SA', 'NSW']
    }
    for adjacent_region in adjacent_regions[region1]:
        if adjacent_region in assignment and assignment[adjacent_region] == color1:
            return False
    return True

# Example usage
variables = ['WA', 'NT', 'SA', 'Q', 'NSW', 'V']
domains = {
    'WA': ['Red', 'Green', 'Blue'],
    'NT': ['Red', 'Green', 'Blue'],
    'SA': ['Red', 'Green', 'Blue'],
    'Q': ['Red', 'Green', 'Blue'],
    'NSW': ['Red', 'Green', 'Blue'],
    'V': ['Red', 'Green', 'Blue']
}
constraints = [not_adjacent_constraint]

map_coloring_csp = MapColoringCSP(variables, domains, constraints)
solution = map_coloring_csp.backtracking_search()
print("Solution:", solution)
