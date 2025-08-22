# Experiment-2
Write a program in Python language for Matrix multiplication fails. Introspect the causes for its failure and write down the possible reasons for its failure. 
## Aim
Write a python program for matrix multiplication and inspect for failures. 

## Algorithm
1.	Start the program.
2. Create empty list formatrix1, matrix2 and result.
3. Get the rows and columns count from the user.
4. Get the values of two matrix.
5. Perform matrix multiplication and store the answer in result.
6. Stop the program. 

## Program
```
def multiply_matrices(matrix1, matrix2):
    r1, c1 = len(matrix1), len(matrix1[0])
    r2, c2 = len(matrix2), len(matrix2[0])

    if c1 != r2:
        raise ValueError("Matrix multiplication not possible")

    result = []
    for i in range(r1):
        row = []
        for j in range(c2):
            total = 0
            for k in range(c1):
                total += matrix1[i][k] * matrix2[k][j]
            row.append(total)
        result.append(row)
    return result


# Only run this part when executing the script directly
if __name__ == "__main__":
    r1, c1 = map(int, input("Enter row and column count for matrix 1: ").split())
    r2, c2 = map(int, input("Enter row and column count for matrix 2: ").split())

    if c1 != r2 or max(r1, c1, r2, c2) > 20 or min(r1, c1, r2, c2) == 0:
        print("Matrix multiplication not possible")
    else:
        print("Enter elements for matrix 1:")
        matrix1 = [[int(input(f"Matrix 1[{i+1}][{j+1}]: ")) for j in range(c1)] for i in range(r1)]

        print("Enter elements for matrix 2:")
        matrix2 = [[int(input(f"Matrix 2[{i+1}][{j+1}]: ")) for j in range(c2)] for i in range(r2)]

        result = multiply_matrices(matrix1, matrix2)

        print("\nResultant Matrix:")
        for row in result:
            print(" ".join(map(str, row)))

```
## Output

<img width="1527" height="269" alt="image" src="https://github.com/user-attachments/assets/212516ba-b42d-4cd0-bf94-5e32b0ab8bb5" />


## Result

Thus, the python program to demonstrate the working of given constructs is implemented and the output is verified successfully.
