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

``` 

# Get the input String
input_string = "huffman coding" 
frequency = {}
for char in input_string:
    if char in frequency:
        frequency[char] += 1
    else:
        frequency[char] = 1

# Create tree nodes
nodes = [[char, freq] for char, freq in frequency.items()]


# Main function to implement huffman coding
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


# Calculate frequency of occurrence
huffman_codes = {}

def generate_codes(tree, code=""):
    if isinstance(tree[0], str):  # If it's a leaf node
        huffman_codes[tree[0]] = code
    else:  # If it's an internal node, recurse
        generate_codes(tree[0][0], code + "0")
        generate_codes(tree[0][1], code + "1")

generate_codes(huffman_tree)


# Print the characters and its huffmancode
print("Character | Huffman Code")
print("-------------------------")
for char, code in huffman_codes.items():
    print(f"    {char}    |    {code}")






```
## Output:

### Print the characters and its huffmancode

<img width="249" height="285" alt="image" src="https://github.com/user-attachments/assets/1c55e959-115e-4799-bf1b-bf76a7e59cba" />



## Result
Thus the huffman coding was implemented to compress the data using python programming.
