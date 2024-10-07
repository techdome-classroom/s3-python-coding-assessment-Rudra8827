def isValid(s: str) -> bool:
    # Dictionary to map closing brackets to their corresponding opening brackets
    bracket_map = {')': '(', ']': '[', '}': '{'}
    
    # Stack to hold the opening brackets
    stack = []
    
    # Traverse each character in the input string
    for char in s:
        # If the character is a closing bracket
        if char in bracket_map:
            # Pop the top element from the stack (or assign '#' if the stack is empty)
            top_element = stack.pop() if stack else '#'
            
            # Check if the popped element matches the corresponding opening bracket
            if bracket_map[char] != top_element:
                return False
        else:
            # If it's an opening bracket, push it to the stack
            stack.append(char)
    
    # If the stack is empty, all opening brackets were matched and closed properly
    return not stack

# Test cases
print(isValid("()"))      # Output: True
print(isValid("()[]{}"))  # Output: True
print(isValid("(]"))      # Output
