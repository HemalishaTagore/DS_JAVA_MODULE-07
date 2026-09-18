# Flattening a Nested List Using an Iterator
## DATE:
## AIM:
To design and implement a class NestedIterator that flattens a nested list of integers such that all integers can be accessed sequentially using an iterator interface (next() and hasNext()).
## Algorithm
1. Start the program.
2. Create a NestedIterator class to store the nested list elements.
3. Recursively traverse the nested list and store all integers in a list.
4. Implement hasNext() to check whether more integers are available.
5. Implement next() to return the next integer sequentially and display the flattened list.

## Program:
```
/*
Program to flatten a nested list using an iterator
Developed by: HEMALISHA T
RegisterNumber: 212225040123
*/

import java.util.*;

class NestedIterator implements Iterator<Integer> {

    private List<Integer> flatList = new ArrayList<>();
    private int index = 0;

    public NestedIterator(List<Object> nestedList) {
        flatten(nestedList);
    }

    private void flatten(List<Object> list) {
        for (Object item : list) {
            if (item instanceof Integer) {
                flatList.add((Integer) item);
            } else {
                flatten((List<Object>) item);
            }
        }
    }

    public boolean hasNext() {
        return index < flatList.size();
    }

    public Integer next() {
        return flatList.get(index++);
    }
}

class FlattenNestedList {

    public static void main(String[] args) {

        List<Object> nestedList = new ArrayList<>();

        nestedList.add(1);
        nestedList.add(Arrays.asList(2, 3));
        nestedList.add(Arrays.asList(4, Arrays.asList(5, 6)));
        nestedList.add(7);

        NestedIterator iterator = new NestedIterator(nestedList);

        System.out.println("Flattened list:");

        while (iterator.hasNext()) {
            System.out.print(iterator.next() + " ");
        }
    }
}
```

## Output:

<img width="168" height="72" alt="image" src="https://github.com/user-attachments/assets/1b08387a-32f6-4e85-ba2b-5ab10949ed56" />


## Result:
The NestedIterator class successfully flattens a nested list of integers into a single list and provides sequential access using standard iterator methods.
