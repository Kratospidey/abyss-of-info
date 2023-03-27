---
{"dg-publish":true,"permalink":"/college/sem-iv/ds/ds-tee-qb/linked-list/ll-programs/"}
---

# Singly Linked List
```c++
#include <iostream>
using namespace std;

class Node
{
public:
    int val;
    Node *next;

    Node(int num)
    {
        this->val = num;
        this->next = nullptr;
    }
};

class LinkedList
{
public:
    Node *head;

    // Constructor
    LinkedList()
    {
        this->head = nullptr;
    }

    // Destructor
    ~LinkedList()
    {
        DelList();
    }

    /**
     * @brief Insert a new node with the given value at the head of the linked list.
     *
     * @param val The value to be inserted at the head of the linked list.
     */
    void InsertAtHead(int val)
    {
        // Create a new node with the given value
        Node *newNode = new Node(val);

        // Set the next pointer of the new node to the current head
        newNode->next = head;

        // Set the head to the new node, making it the new head of the linked list
        head = newNode;
    }

    /**
     * @brief Deletes the first node in the linked list and returns its value.
     *
     * @return An integer representing the value of the deleted node. If the list
     *         is empty, returns -999.
     */
    int DeleteAtHead()
    {
        // Returns -999 if list is empty
        if (head == nullptr)
        {
            return -999;
        }

        // Store the head node temporarily
        Node *tmp = head;

        // Get the value of the head node
        int num = head->val;

        // Move the head pointer to the next node
        head = head->next;

        // Delete the previous head node
        delete tmp;

        // Return the value of the deleted node
        return num;
    }

    /**
     * @brief Inserts a new node with the given value at the end of the linked list.
     *
     * @param val The value to be inserted.
     *
     * @return void
     */

    void InsertAtTail(int val)
    {

        // Create new node with the given value
        Node *newNode = new Node(val);

        // If the linked list is empty, set head to the new node
        if (head == nullptr)
        {
            head = newNode;
            return;
        }

        // Traverse the linked list to find the last node
        Node *tmp = head;

        for (; tmp->next != nullptr; tmp = tmp->next)
        {
            ;
        }

        // Set the next of the last node to the new node
        tmp->next = newNode;
    }

    /**
     * @brief Delete the last element of the linked list and returns its value.
     *
     * @return the value of the deleted node if successful, otherwise -999
     */
    int DeleteAtTail()
    {
        // If the linked list is empty.
        if (head == nullptr)
        {
            return -999;
        }

        // If there is only one node in the linked list.
        if (head->next == nullptr)
        {
            int num = head->val;
            delete head;
            head = nullptr;
            return num;
        }

        // Traverse the linked list until we reach the second last node.
        Node *prev = head, *cur = head->next;
        while (cur->next != nullptr)
        {
            prev = cur;
            cur = cur->next;
        }

        // Delete the last node and update the second last node's next pointer.
        int num = cur->val;
        delete cur;
        prev->next = nullptr;
        return num;
    }

    /**
     * @brief Inserts a node with the given value at the specified position in the linked list.
     *
     * @param val the value to be inserted in the linked list
     * @param pos the position at which the value is to be inserted
     * @return void
     */
    void InsertAtPos(int val, int pos)
    {
        int cur = 1, count = 1;

        Node *newNode = new Node(val);

        // case for empty list
        if (head == nullptr)
        {
            head = newNode;
            return;
        }

        // Count number of elements in list
        for (Node *temp = head; temp->next != nullptr; temp = temp->next)
        {
            count++;
        }

        // If list is smaller than position given, insert at tail
        // ! why do this??
        if (count < pos)
        {
            delete newNode;
            InsertAtTail(val);
            return;
        }

        // Insert at pos specified
        for (Node *temp = head; temp->next != nullptr; temp = temp->next)
        {
            if (cur == pos)
            {
                newNode->next = temp->next;
                temp->next = newNode;
                return;
            }
            cur++;
        }
    }

    /**
     * @brief Deletes the node at the specified position in the linked list.
     *
     * @param pos The zero-based position of the node to delete.
     * @return The value of the deleted node, or -999 if the list is empty
     *         or the position is invalid.
     */
    int DeleteAtPos(int pos)
    {

        // If the list is empty, there is nothing to delete
        if (head == nullptr)
        {
            return -999;
        }

        // Start from the head node
        Node *before = head;

        // If the head node needs to be deleted
        if (pos == 0)
        {
            // Store the value of the node to be deleted
            int num = before->val;

            // Move the head to the next node
            head = before->next;

            // Free the memory of the deleted node
            delete before;

            // Return the value of the deleted node
            return num;
        }

        // Find the node immediately before the one to be deleted
        for (int i = 0; before != nullptr && i < pos - 1; i++)
        {
            before = before->next;
        }

        // If the position is invalid, return -999
        if (before == nullptr || before->next == nullptr)
        {
            return -999;
        }

        // Store the node after the one to be deleted
        Node *after = before->next->next;

        // Store the value of the node to be deleted
        int num = before->next->val;

        // Free the memory of the deleted node
        delete before->next;

        // Reconnect the linked list
        before->next = after;

        // Return the value of the deleted node
        return num;
    }

    /**
     * @brief Deletes all nodes in the linked list and sets the head pointer to nullptr.
     *
     * @param none
     *
     * @return void
     */
    void DelList()
    {
        // If linked list is empty, return immediately
        if (head == nullptr)
        {
            return;
        }

        // Set pointers to traverse the linked list
        Node *cur = head;
        Node *ahead = head->next;

        // Traverse the linked list and delete each node
        while (ahead != nullptr)
        {
            delete cur;
            cur = ahead;
            ahead = ahead->next;
        }

        // Delete the last node and set head to nullptr
        delete cur;
        head = nullptr;
        return;
    }

    /**
     * @brief Displays the linked list starting from the head node.
     *
     * @param none
     *
     * @return void
     */

    void Display()
    {
        // If the linked list is empty
        if (head == nullptr)
        {
            cout << "Nothing in list" << endl;
            return;
        }

        // Print all the node values
        cout << "Linked List: ";
        for (Node *cur = head; cur != nullptr; cur = cur->next)
        {
            cout << cur->val << " ";
        }
        cout << endl;
        return;
    }
};

int main()
{
    LinkedList a;
    int choice, num, pos;
    do
    {
        cout << endl
             << "Menu:" << endl
             << "1. Insert at Head" << endl
             << "2. Insert At Tail" << endl
             << "3. Delete at Head" << endl
             << "4. Delete at Tail" << endl
             << "5. Insert at Position" << endl
             << "6. Delete at Position" << endl
             << "7. Display" << endl
             << "8. Delete list" << endl
             << "9. Quit" << endl
             << "$ ";
        cin >> choice;

        switch (choice)
        {
        case 1:
            cout << "Value to insert: ";
            cin >> num;
            a.InsertAtHead(num);
            break;
        case 2:
            cout << "Value to insert: ";
            cin >> num;
            a.InsertAtTail(num);
            break;
        case 3:
            cout << a.DeleteAtHead() << endl
                 << endl;
            break;
        case 4:
            cout << a.DeleteAtTail() << endl
                 << endl;
            break;
        case 5:
            cout << "Position to insert value: ";
            cin >> pos;
            cout << "Value to insert: ";
            cin >> num;
            a.InsertAtPos(num, pos);
            break;
        case 6:
            cout << "Position to delete value: ";
            cin >> pos;
            cout << a.DeleteAtPos(pos) << endl
                 << endl;
            break;
        case 7:
            a.Display();
            cout << endl
                 << endl;
            break;
        case 8:
            a.DelList();
            break;
        case 9:
            break;
        default:
            cout << "Invalid option" << endl;
        }
    } while (choice != 9);
}
```