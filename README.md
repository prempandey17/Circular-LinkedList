//Circular-LinkedList
import java.util.Scanner;
public class Circular_LinkedList
{
   static class Node
    {
        int data;
        Node next;
        Node(int data)
        {
            this.data=data;
            this.next=null;
        }
    }  
    
    static Node head=null;
    static Node tail=null;

    static void insert()
    {
        int data,choice;
        Scanner sc=new Scanner(System.in);
        do
        {
        System.out.println("Enter Data: ");
        data=sc.nextInt();
        Node new_node=new Node(data);
        if(head==null)
        {
            head=new_node;
            tail=new_node;
            new_node.next=head;
        }
        else
        {
            new_node.next=head;
            head=new_node;
            tail.next=head;
        }
        System.out.println("If ypu want to enter more data press 0:");
        choice=sc.nextInt();
    }while(choice==0);
   }

   static void traverse()
   {
      Node temp=head; 
      if(head==null)
      {
         System.out.println("Empty ");
      }
      else
      {
          
          System.out.print(" Givem Data : ");
          do
          
          {
             System.out.print(temp.data+"  ");
             temp=temp.next;
          }while(temp!=head);   
      }
   }

    static void delete()
    {
       
        if(head==null)
        {
             System.out.println("Empty list: ");
        }
        else
        {
            Scanner sc=new Scanner(System.in);
            System.out.println("Press 1 for deletion from begining: ");
            System.out.println("Press 2 for deletion from last: ");
            System.out.println("Press 3 for deletion from specific position: ");
            

            int n=sc.nextInt();

            switch(n)
            {
                case 1:
                   head=head.next;
                   tail.next=head;
                   break;
                case 2:
                    Node ptr1=null;
                    Node ptr=head;
                   while(ptr.next!=head)
                   {
                       ptr1=ptr;
                       ptr=ptr.next;
                   }
                   ptr1.next=ptr.next;
                   tail.next=head;
                   tail=head;
                   break;
                case 3:
                System.out.println("Enter postion values that you want to delete: ");
                int pos=sc.nextInt();
                Node ptr3=null;
                Node ptr2=head;
                for(int i=1;i<pos;i++)
                {
                    ptr3=ptr2;
                    ptr2=ptr2.next;
                }
                ptr3.next=ptr2.next;
              //  if(ptr2.next==head)
               // {
                 //   tail=
                //}
            }
        }
    }
    public static void main(String[] args)
    {
        Scanner s=new Scanner(System.in);
        int choice1;
       do
       { 
        System.out.println("Press 1 for insert data:");
        System.out.println("Press 2 for delete data:");
        System.out.println("press 3 for show data:");
        int n1=s.nextInt();
        switch(n1)
        {
            case 1:
               insert();
               break;
            case 2:
               delete();
               break;
            case 3:       
               traverse();
               break;
        }
        System.out.println("If you want to continue process then press 0 :");
        choice1=s.nextInt();
      }while(choice1==0);
    }
   
}
