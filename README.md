# Identical-LL
Check if two linked list are identical or not i.e their elements are same and arranged in same order
//Lists are identical or not
#include<iostream>
using namespace std;

struct Node{
	int data;
	Node *next;
	Node(int d){
		data=d;
		next=NULL;
	}
};

Node* insertAtEnd(Node* head,int y){
	Node* temp = new Node(y);
	if(head==NULL){
		return temp;
	}
	Node* curr=head;
	while(curr->next!=NULL){
		curr=curr->next;
	}
	curr->next=temp;
	return head;
}

bool checkIdentical(Node* head1,Node* head2){
	Node* curr1=head1;
	Node* curr2=head2;
	while(curr1!=NULL && curr2!=NULL){
		if(curr1->data!=curr2->data){
			return false;
		}
		curr1=curr1->next;
		curr2=curr2->next;
	}
	return true;
}

void printList(Node* head){
	Node* curr=head;
	while(curr!=NULL){
		cout<<curr->data;
		curr=curr->next;
	}
}

int main(){
	Node* head1=NULL;
	int n1;
	cin>>n1;
	for(int i=1;i<=n1;i++){
		int x;
		cin>>x;
		head1=insertAtEnd(head1,x);
	}
	Node* head2=NULL;
	int n2;
	cin>>n2;
	for(int i=1;i<=n2;i++){
		int x;
		cin>>x;
		head2=insertAtEnd(head2,x);
	}
	printList(head1);
	cout<<endl;
	printList(head2);
	cout<<endl;
	cout<<"List are indentical: "<<checkIdentical(head1,head2);
	
}
