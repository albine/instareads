---
name: Reverse Linked List
---
```java
public class RLL {
    public static void reverse(Node head) {
        if (head == null || head.next = null) return head;

        Node dummy = new Node();
        dummy.next = head;

        Node pre = dummy;
        Node cur = head;

        while (cur.next != null) {
            Node tmp = cur.next;
            cur.next = pre;
            pre = cur;
            cur = tmp;
        }

        cur.next = pre;
        head.next = null;
        return cur;
    }
}
```