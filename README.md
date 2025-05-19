# Huffman-Coding
## Aim
To implement Huffman coding to compress the data using Python.

## Software Required
1. Anaconda - Python 3.7

## Algorithm:
### Step1:
Get the input string.

### Step2:
Create tree nodes.

### Step3:
Main function to implement huffman coding.

### Step4:
calculate frequency of occurence.

### Step5:
print the characters and its huffmancode.
 
## Program:

``` Python
# expt-11-huffman coding

# Step 1: Get the input string
input_string = "huffman coding"  # Example input string
# Step 2: Calculate frequency of each character in the input string
frequency = {}
for char in input_string:
    if char in frequency:
        frequency[char] += 1
    else:
        frequency[char] = 1
# Step 3: Create tree nodes
nodes = [[char, freq] for char, freq in frequency.items()]
# Step 4: Main function to implement Huffman coding
while len(nodes) > 1:
    # Sort nodes based on frequency
    nodes = sorted(nodes, key=lambda x: x[1])

    # Pick two smallest nodes
    left = nodes.pop(0)
    right = nodes.pop(0)

    # Create a new node with combined frequency
    new_node = [[left, right], left[1] + right[1]]
    nodes.append(new_node)

# The final node is the Huffman tree
huffman_tree = nodes[0]
# Step 5: Generate Huffman codes
huffman_codes = {}

def generate_codes(tree, code=""):
    if isinstance(tree[0], str):  # If it's a leaf node
        huffman_codes[tree[0]] = code
    else:  # If it's an internal node, recurse
        generate_codes(tree[0][0], code + "0")
        generate_codes(tree[0][1], code + "1")

generate_codes(huffman_tree)
# Step 6: Print the characters and their Huffman codes
print("Character | Huffman Code")
print("-------------------------")
for char, code in huffman_codes.items():
    print(f"    {char}    |    {code}")

```
## Output:

![Screenshot 2025-05-19 114009](https://github.com/user-attachments/assets/1b985389-ba01-4ae6-9525-1a5d259e5ba2)

![Screenshot 2025-05-19 114023](https://github.com/user-attachments/assets/2f352c0a-cd89-47d5-8831-990f98b7024e)

![Screenshot 2025-05-19 114037](https://github.com/user-attachments/assets/8f23177a-bc08-4ad2-acc9-04de2ccfe9b0)

![Screenshot 2025-05-19 114052](https://github.com/user-attachments/assets/1229692e-d0ba-4ebb-a4c3-4bc89842c496)

![Screenshot 2025-05-19 114105](https://github.com/user-attachments/assets/cb366fe9-11ab-4c8d-83ce-a012f0e8e868)

![Screenshot 2025-05-19 114119](https://github.com/user-attachments/assets/0ce05397-5d66-413f-8a70-a08f82c583ab)

## Result
Thus, the huffman coding was implemented to compress the data using python programming.
