# Linked List:
- **list/head**
   - This is usually the head/top of your list, the beginning of your list, the first node in your list

- **Node p = list;**
   - Puts p on the same node as list or head so that you can start going through the list
   - This is usually used when you want to start going through your list, you make p equal to list or head to make sure that list always knows where the beginning of the list is
      - **Note:** if you move list, in other words, list = list.next, you are changing the first node to become the next node, so if you have 2 nodes and node1 is connected to node2, and node1 is the first node in your list, list = list.next will make the first node node2 and node1 will be deleted because you wont be able to use it anymore

- **p = p.next;**
   - Moves p to the next node
   - This is usually used to go through the list

- **p.next = new Node(3, null)**
   - This will create a new node and add it to the **end** of your list
   - How it works:
      - **First**
      ```
      new Node(3, null)
      ```
      A new node will be created with a value of *__3__*, and the next node will be null, because when creating a new node in the list, typically that node is added to the end of the list, and if you are adding a node to the end of your list you know that it is the last node in your list (until you add another node to your list)

      - **Second**
      ```
      p.next = new Node(3, null);
      ```
      After the new node is created, you are telling node **p** that the new next node in your list is going to be the new node you just created (node3) so connect to it, in other words, you are connecting p's next to the new node

- **p != null**
   - This is usually used in **if statements** or **while loops** to check when you are supposed to stop going through your list
   ```
   // this if statement would go inside your while or for loop
   if (p != null) {
      // code to be executed, usually a break (break;)
   }
   ```
   or
   ```
   while (p != null) {
      // code to be executed
   }
   ```
   - This case usually involves another node **q** that will stay in the list when **p** goes out of the list, or when p becomes null

- **p.next != null**
   - This is similar to **p != null**, the only difference here is you dont need another node like **q** to stay in your list, but you will have to have an if statement before your while loop to check if a first node exists
   ```
   if (list == null) {
      // create first node
   } else {
      while (p.next != null) {
         // go through list
      }
   }
   ```

- **Going through list with __p__ and __q__ to add a new node**
   - When you want to go through your list, you will typically use nodes **p** and **q** to help you go through it
   ```
   Node p = list;
   Node q = null;
   if (list == null) {
      list = new Node(item, null);
   } else {
      while (p != null) {
         q = p;
         p = p.next;
      }
      q.next = new Node(item, null)
   }
   ```
   Heres whats happening:
   - **First**
   ```
   Node p = list;
   ```
   The first step in going through your list is to make sure p gets placed on the first node, this code will make sure that p is on the first node, and list (which is the thing that is keeping track of the first node in your list) doesnt change at all
   - **Second**
   ```
   Node q = null;
   ```
   **q** is just a helper node that will stay in your list when you are going through the list, it is initially set to null because you dont have a node to put it on yet, you need to make sure that the list has a first node before you put **q** on it.
   - **Third**
   ```
   if (list == null) {
      list = new Node(1, null);
   }
   ```
   before going through the list, you want to check if you actually have something in your list, this if statement will check your list to see if its empty or not, for example, lets say you are building a shopping list, before you start writing down the things you need to buy, your shopping list is empty, you dont have a first item to buy, the if statement will check if you have anything on your list, if you dont have a first item, the if statement will create the first item for you
   - **Fourth**
   ```
   else {
      while (p != null) {
   ```
   now you know that theres at least 1 node in your list, so you know that p is sitting on a node, but when you are going through your list, p will be moved to the next node, eventually p will get to the end of the list and go to the next node, but if you try to get to the next node when you are at the end of your list, there is no next node which means that p will leave or get out of your list so p will become null, this code will make sure that when p gets out of the list, it will stop going through the list
   - **Next**
   ```
   q = p;
   ```
   now that you know there is at least one node in your list, and you know that **p** will eventually leave the list, you need to have something that is going to stay in the list to allow you to add a new node to the end of it, **q** will do just that, **q = p** will put **q** on the node that **p** is on right now so that when **p** leaves the list, you know that **q** is still in the list
   - **Next**
   ```
   p = p.next;
   ```
   **p** will now move to the next node in the list
   - **Finally**
   ```
   q.next = new Node(item, null);
   ```
   after you go through the list and **p** gets out of the list, you know that **q** is still in the list, so you can just tell **q** to create a new node and connect it to the list