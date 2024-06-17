#include <stdio.h>
#include <stdlib.h>

typedef struct Node {
    int data;
    struct Node *next;
} Node;

typedef struct {
    Node *top;
} StackList;

// Initialize the stack
void initStackList(StackList *s) {
    s->top = NULL;
}

// Check if the stack is empty
int isEmptyList(StackList *s) {
    return s->top == NULL;
}

// Push an element into the stack
void pushList(StackList *s, int value) {
    Node newNode = (Node)malloc(sizeof(Node));
    if (!newNode) {
        printf("Heap overflow\n");
        return;
    }
    newNode->data = value;
    newNode->next = s->top;
    s->top = newNode;
}

// Pop an element from the stack
int popList(StackList *s) {
    if (isEmptyList(s)) {
        printf("Stack is empty\n");
        return -1;
    }
    Node *temp = s->top;
    s->top = s->top->next;
    int popped = temp->data;
    free(temp);
    return popped;
}

// Return the topmost element from the stack
int topList(StackList *s) {
    if (isEmptyList(s)) {
        printf("Stack is empty\n");
        return -1;
    }
    return s->top->data;
}

// Display the elements in the stack
void displayList(StackList *s) {
    if (isEmptyList(s)) {
        printf("Stack is empty\n");
        return;
    }
    Node *temp = s->top;
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

// Main function to demonstrate stack operations using linked list
int main() {
    StackList stack;
    initStackList(&stack);

    pushList(&stack, 10);
    pushList(&stack, 20);
    pushList(&stack, 30);

    printf("Stack elements: ");
    displayList(&stack);

    printf("Top element: %d\n", topList(&stack));

    printf("Popped element: %d\n", popList(&stack));
    printf("Stack elements after pop: ");
    displayList(&stack);

    return 0;
}
