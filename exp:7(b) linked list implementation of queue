#include <stdio.h>
#include <stdlib.h>

// Node structure
typedef struct Node {
    int data;
    struct Node *next;
} Node;

// Queue structure using linked list
typedef struct {
    Node *front, *rear;
} QueueList;

// Initialize the queue
void initQueueList(QueueList *q) {
    q->front = q->rear = NULL;
}

// Check if the queue is empty
int isEmptyList(QueueList *q) {
    return q->front == NULL;
}

// Enqueue an element into the queue
void enqueueList(QueueList *q, int value) {
    Node newNode = (Node)malloc(sizeof(Node));
    if (!newNode) {
        printf("Memory allocation error\n");
        return;
    }
    newNode->data = value;
    newNode->next = NULL;
    if (q->rear == NULL) {
        q->front = q->rear = newNode;
    } else {
        q->rear->next = newNode;
        q->rear = newNode;
    }
}

// Dequeue an element from the queue
int dequeueList(QueueList *q) {
    if (isEmptyList(q)) {
        printf("Queue is empty\n");
        return -1;
    }
    Node *temp = q->front;
    int data = temp->data;
    q->front = q->front->next;
    if (q->front == NULL) {
        q->rear = NULL;
    }
    free(temp);
    return data;
}

// Display the elements in the queue
void displayList(QueueList *q) {
    if (isEmptyList(q)) {
        printf("Queue is empty\n");
        return;
    }
    Node *temp = q->front;
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

// Main function to demonstrate queue operations using linked list
int main() {
    QueueList queue;
    initQueueList(&queue);

    enqueueList(&queue, 10);
    enqueueList(&queue, 20);
    enqueueList(&queue, 30);

    printf("Queue elements: ");
    displayList(&queue);

    printf("Dequeued element: %d\n", dequeueList(&queue));
    printf("Queue elements after dequeue: ");
    displayList(&queue);

    return 0;
}
