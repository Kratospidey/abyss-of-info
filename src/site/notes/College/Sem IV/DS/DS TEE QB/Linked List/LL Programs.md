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

# Linear Queue
```c++
#include <iostream>

using namespace std;

  

class Node {

	public:

	int val;
	
	Node *next;

  

	Node(int n) {
	
		this->next = nullptr;
		
		this->val = n;
	
	}

};

  

class LinkedList {

	public:
	
	Node *head, *tail;
	
	  
	
	//Constructor
	
	LinkedList() {
	
		head = nullptr;
		
		tail = nullptr;
	
	}
	
	  
	
	//Aux Function
	
	bool IsEmpty() {
	
		return head == nullptr && tail == nullptr;
		
	}
		
		  
		
	int Size() {
		
		if (IsEmpty()) {
		
			return 0;
		
		}
		
		int counter = 0;
		
		for (Node *tmp = head; tmp != nullptr; tmp = tmp->next) {
		
			++counter;
		
		}
		
		return counter;
	
	}
	
	  
	
	//Main Functions
	
	void InsertAtHead(int n) {
	
		Node *newnode = new Node(n);
		
		newnode->next = head;
		
		head = newnode;
		
		return ;
	
	}
	
	  
	
	void InsertAtTail(int n) {
	
		Node *newnode = new Node(n);
		
		if (tail == nullptr && head == nullptr) {
		
			head = tail = newnode;
		
			return ;
		
		}
		
		tail->next = newnode;
		
		tail = newnode;
		
		return ;
	
	}
	
	  
	
	int DeleteAtFront() {
	
		// Case for Empty list
		
		if (head == nullptr) {
		
			return -999;
		
		}
		
		int val = head->val;
		
		// Case for one node
		
		if (head == tail) {
		
			delete head;
			
			head = tail = nullptr;
			
			return val;
		
		}
		
		Node *temp = head;
		
		head = head->next;
		
		// Check if the new head pointer points to the last node in the list
		
		if (head->next == nullptr) {
		
			tail = head;
		
		}
		
		delete temp;
		
		return val;
	
	}
	
	  
	
	void DeleteAtTail(){
	
		if (head == nullptr){
		
			return ;
		
		}
		
		if (head->next == nullptr) {
		
			delete head;
			
			head = nullptr;
			
			return ;
		
		}
		
		Node *prev = head;
		
		Node *cur = head->next;
		
		while (cur->next != nullptr) {
		
			prev = cur;
			
			cur = cur->next;
		
		}
		
		delete cur;
		
		prev->next = nullptr;
		
		tail = prev;
		
		return ;
	
	}
	
	  
	
	void DeleteList(){
		
		if (head == nullptr) {
		
			return ;
		
		}
		
		Node *cur = head;
		
		Node *ahead = head->next;
		
		while (ahead != nullptr) {
		
			delete cur;
		
			cur = ahead;
			
			ahead = ahead->next;
		
		}
		
		delete cur;
		
		head = nullptr;
		
		return ;
	
	}
	
	  
	
	//Destructor
	
	~LinkedList(){
	
		if (head == nullptr) {
		
			return ;
		
		}
		
		Node *cur = head;
		
		Node *ahead = head->next;
		
		while (ahead != nullptr) {
		
			delete cur;
			
			cur = ahead;
			
			ahead = ahead->next;
		
		}
		
		delete cur;
		
		head = nullptr;
		
		return ;
	
	}
	
	  
	
	void Display() {
	
		if (head == nullptr) {
		
			cout<<"Empty Queue"<<endl;
			
			return ;
		
		}
		
		cout<<"Queue: ";
		
		for (Node *cur = head; cur != nullptr; cur = cur->next) {
		
			cout<<cur->val<<" ";
		
		}
		
		cout<<endl;
		
		return ;
		
	}

};

  

class Queue {

	public:
	
	LinkedList list;
	
	Node *head, *tail;
	
	  
	
	//Constructor
	
	Queue() {
	
		head = list.head;
		
		tail = list.tail;
	
	}
	
	  
	
	//Aux Functions
	
	bool IsEmpty() {
	
		return list.IsEmpty();
	
	}
	
	  
	
	int Size() {
	
		return list.Size();
	
	}
	
	  
	
	int Front() {
	
		if (IsEmpty()) {
		
			return 0;
		
		}
		
		return head->val;
	
	}
	
	  
	
	//Main Functions
	
	void Enqueue(int n) {
	
		list.InsertAtTail(n);
		
		return ;
	
	}
	
	  
	
	int Dequeue() {
	
		if (IsEmpty()) {
		
			cout<<"Queue Underflow"<<endl;
			
			return -999;
		
		}
		
		int num = list.DeleteAtFront();
		
		cout<<endl<<"Dequeued"<<endl<<endl;
		
		return num;
	
	}
	
	  
	
	void Display() {
	
		list.Display();
	
	}
	
	  
	
	//Destructor
	
	~Queue() {
		
		list.DeleteList();
		
		return ;
	
	}

};

  

int main() {

	Queue a;
	
	int choice, num = 0;
	
	while (choice != 5) {
	
		cout<<"1. Enqueue"<<endl
		
		<<"2. Dequeue"<<endl
		
		<<"3. Display"<<endl
		
		<<"4. Size"<<endl
		
		<<"5. Quit"<<endl
		
		<<"$ ";
		
		cin >> choice;
		
		switch(choice) {
		
			case 1:
			
				cout<<"Number: ";
				
				cin >> num;
				
				a.Enqueue(num);
				
				cout<<endl;
			
				break;
			
			case 2:
			
				a.Dequeue();
				
				break;
			
			case 3:
			
				cout<<endl;
				
				a.Display();
				
				cout<<endl;
				
				break;
			
			case 4:
			
				cout<<endl<<"Size: "<<a.Size()<<endl<<endl;
			
				break;
			
			case 5:
			
				break;
			
			default:
			
				cout<<"Invalid Input"<<endl<<endl;
		
		}
	
	}
	
	cout<<a.Front()<<endl;
	
	return 0;

}
```

# Stack
```c++
#include <iostream>

using namespace std;

  

class Node {

	public:
	
	int val;
	
	Node *next;
	
	  
	
	// Constructor
	
	Node(int num) {
	
		val = num;
		
		next = nullptr;
	
	}

};

  

class LinkedList {

	public:
	
	Node *head, *tail;
	
	// Constructor
	
	LinkedList() {
	
		head = tail = nullptr;
	
	}
	
	  
	
	void InsertAtHead(int num) {
	
		Node *newNode = new Node(num);
		
		// Case for first node
		
		if (head == nullptr) {
		
			head = tail = newNode;
		
		return ;
	
		}
	
		newNode->next = head;
		
		head = newNode;
	
	}
	
	  
	
	int DeleteAtHead() {
	
		// Case for empty list
		
		if (head == nullptr) {
		
			return -999;
		
		}
		
		int num = head->val;
		
		Node *temp = head;
		
		  
		
		// Case for one node
		
		if (head == tail) {
		
			head = tail = nullptr;
		
		}
		
		else {
		
			head = head->next;
		
		}
		
		delete temp;
		
		return num;
	
	}
	
	  
	
	void InsertAtTail(int num) {
	
		Node *newNode = new Node(num);
		
		  
		
		// Case for first node
		
		if (tail == nullptr) {
		
			tail = head = newNode;
		
			return ;
	
		}
	
	  
	
		tail->next = newNode;
		
		tail = tail->next;
		
		return ;
	
	}
	
	  
	
	int DeleteAtTail() {
	
		// Case for empty list
		
		if (tail == nullptr) {
		
			return -999;
		
		}
		
		  
		
		Node *temp = tail;
		
		int num = tail->val;
		
		  
		
		//Case for one node
		
		if (tail == head) {
		
			tail = head = nullptr;
		
		}
		
		else {
		
			Node *tmp = head;
			
			for (; tmp->next != tail; tmp = tmp->next) {
			
				;
			
			}
			
			tail = tmp;
		
		}
		
		delete temp;
		
		return num;
	
	}
	
	  
	
	void InsertAtPos(int val, int pos) {
		
		int cur = 1; // Keep track of current node number
		
		if (head == nullptr) {
		
		return ;
		
		}
		
		Node *newNode = new Node(val);
		
		// Traverse through list till last element while checking for position to insert
		
		for (Node *temp = head; temp->next != nullptr; temp = temp->next) {
		
			if (cur == pos) {
			
				newNode->next = temp->next;
				
				temp->next = newNode;
				
				return ;
			
			}
		
		cur++;
		
		}

	}

  

	int DeleteAtPos(int pos) {
	
		// Check if list is empty
		
		if (head == nullptr) {
		
			cout<<"List is empty"<<endl;
		
			return -999;
	
		}

		// This will be before the target node
		
		Node *before = head;
		
		// Traverse the list until you either run out of nodes or reach the node required
		
		for (int i = 1; before != nullptr && i < pos - 1; i++, before = before->next) {
		
			;
		
		}
		
		// If the list is shorter than the position to delete
		
		if (before == nullptr || before->next == nullptr) {
		
			cout<<"List is shorter than given position"<<endl;
		
			return -999;
	
	}

		// This node is after the target node
		
		Node *after = before->next->next;
		
		int val = before->next->val;
		
		delete before->next;
		
		before->next = after;
		
		return val;

	}

  

	void DelList() {
	
		if (head == nullptr){
		
			return ;
		
		}
		
		Node *cur = head;
		
		Node *ahead = head->next;
		
		while (ahead != nullptr) {
		
			delete cur;
			
			cur = ahead;
			
			ahead = ahead->next;
		
		}
		
		delete cur;
		
		head = nullptr;
		
		return ;
	
	}

  

	void Display() {
	
		if (head == nullptr) {
		
			cout<<"Nothing in list"<<endl;
			
			return ;
		
		}
		
		cout<<"Stack: ";
		
		for (Node *cur = head; cur != nullptr; cur = cur->next){
		
			cout<<cur->val<<" ";
		
		}
		
		cout<<endl;
		
		return ;
	
	}
	
	  
	
	~LinkedList() {
	
		DelList();
	
	}

};

  

class Stack {

	public:
	
	LinkedList list;
	
	  
	
	//Auxilary Functions
	
	  
	
	bool IsEmpty() {
	
		return list.head == nullptr && list.tail == nullptr;
	
	}
	
	  
	
	int Size() {
	
		int count = 1;
		
		for (Node *temp = list.head; temp != nullptr; temp = temp->next, count++) {
		
			;
		
		}
		
		return count;
	
	}
	
	int Peek() {
	
		if (IsEmpty()) {
		
			return -999;
	
		}
	
		int num = list.head->val;
		
		return num;
	
	}
	
	  
	
	// Main Functions 
	
	void Push(int a) {
	
		list.InsertAtHead(a);
	
	}



	int Pop() {
	
		int result = list.DeleteAtHead();
		
		if (result == -999) {
		
			cout<<"Stack Underflow"<<endl;
		
		} else {
		
			cout<<"Popping Stack"<<endl;
			
			cout<<"Popped number: "<<result<<endl;
		
		}
		
		return result;
	
	}
	
	  
	
	void Display() {
	
		list.Display();
	
	}

  

};

  

int main() {

	int choice, num;
	
	Stack a;
	
	do {
	
		cout<<"1. Push"<<endl
		
		<<"2. Pop"<<endl
		
		<<"3. View Stack"<<endl
		
		<<"4. Quit"<<endl<<endl
		
		<<"Choice: ";
		
		cin>>choice;
		
		switch(choice){
		
			case 1:
			
				cout<<"Enter Number: ";
				
				cin>>num;
				
				a.Push(num);
			
				break;
			
			case 2:
			
				a.Pop();
				
				break;
			
			case 3:
			
				a.Display();
				
				break;
			
			case 4:
			
				break;
			
			default:
			
				cout<<"Invalid Option"<<endl;
		
		}
	
	}
	
	while (choice != 4);

}
```