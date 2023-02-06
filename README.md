// AppendLastNToFirst
// You have been given a singly linked list of integers along with an integer 'N'. Write a function to append the last 'N' nodes towards the front of the singly linked list and returns the new head to the list.

/*

	Following is the Node class already written for the Linked List

	class LinkedListNode<T> {
    	T data;
    	LinkedListNode<T> next;
    
    	public LinkedListNode(T data) {
        	this.data = data;
    	}
	}

*/

public class Solution {

	public static LinkedListNode<Integer> appendLastNToFirst(LinkedListNode<Integer> head, int n) {
		
		int pos = counte(head);
		int count = 1;
		LinkedListNode<Integer> temp = head;
		LinkedListNode<Integer> nhead = null;
		LinkedListNode<Integer> ntail = null;
		if (head == null || n == 0) {
			return head;
		}
		while (temp.next != null) {
			if (count == (pos - n)) {
				ntail = temp;

			}
			if (count == (pos - n + 1)) {
				nhead = temp;
			}

			temp = temp.next;
			count++;
		}

		ntail.next = null;
		temp.next = head;
		return nhead;
	}

	// return total no. of element in linklist
	public static int counte(LinkedListNode<Integer>head) {
		int count=0;
		if(head==null) {
			return count;
		}
		LinkedListNode<Integer>temp=head;
		while(temp!=null) {
			count++;
			temp=temp.next;
		}
		return count;
	}
}
