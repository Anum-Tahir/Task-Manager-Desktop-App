# Project-Mid-Report
//JAVA code 
//Anum Tahir, Nayab Javed

class node {
	public
    int data;				//event details
    String description;
    String time;
    String date;
    int priority;
    
    public
    node()
    {
    	data = 0;
    	priority = 0;
    }
}

class stack {					
	private           //for priority queues (to rearrange the elements of queue)
	static final int size =100;
	int[] array = new int[size];
	int top;
	
	public
	stack()
	{
		top = -1;    //setting the top intially to -1
	}
	
	boolean is_full()
	{
		if (top == (size - 1))
			return true;

		else
			return false;

	}
	boolean stack_is_empty()
	{
		if (top == -1)
			return true;
		else
			return false;
	}
	
	void push(int val)			//to add an element into the stack
	{
		if (is_full() == true)
		{
			System.out.println("stack overflow");
		}
		else
		{
			top++;
			array[top] = val;
		}
	}
	
	void pop()				//to remove an element from the stack
	{
		if (stack_is_empty() == true)
		{
			System.out.println("stack underflow");
		}
		else
		{
			top--;
		}

	}
	int get_top_data()
	{
		if (stack_is_empty())
			return -1;
		if (is_full())
			return 0;
		else

			return array[top];
	}

}

class queues		
{
private
	static final int size = 100;
	int[] array=new int[size];
	int front;
	int last;
	stack s;
	node n;
public
	queues()
	{
		front = -1;
		last = -1;
	}

	boolean is_empty()
	{
		if (front == -1)
			return true;
		else
			return false;
	}

	void insert(int v)
	{
		if (is_empty())
		{
			front++;
			last++;
			array[front] = v;
		}
		else
		{
			last++;
			array[last] = v;
		}
	}
	void remove()
	{
		if (is_empty())
		{
			System.out.println("stack underflow");
		}
		else
		{
			array[front] = 0;
			front++;
		}
	}
	int get_first()
	{
		if (is_empty())
		{
			System.out.println("queue is empty");
			return 0;
		}
		else
		{
			return array[front];
		}
	}

	void priority_queue(int v)			//to set the priorties of tasks to perform
	{
		
		switch (n.priority)
		{
		case '1':
			insert(v);
			break;
		case '2':

			while (n.priority != 2)
			{
				s.push(get_first());
				remove();
			}
			insert(v);
			while (!s.stack_is_empty())
			{
				insert(s.get_top_data());
			}
			break;
		case '3':
			while (n.priority != 3)
			{
				s.push(get_first());
				remove();
			}
			insert(v);
			while (!s.stack_is_empty())
			{
				insert(s.get_top_data());
			}
			break;

		}
	}
}

public class Main {
	/**
	 * @param args
	 */
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
		stack S1=new stack();			//testing member functions of stack
		System.out.println("push");
		S1.push(5);
		S1.push(4);
		S1.push(3);
		S1.push(2);
		S1.push(1);
		System.out.println("get top value");
		System.out.println(S1.get_top_data());
		System.out.println("\n\n\n");

		System.out.println("copy constructor");
		stack S2 = S1;
		S2.push(9);
		System.out.println("get top value");
		System.out.println(S1.get_top_data());
		System.out.println("\n\n\n");

		System.out.println("copy constructor");
		S1.pop();
		System.out.println("\n");

		System.out.println("get top value");
		System.out.println(S1.get_top_data());
		System.out.println("\n");
		queues Q1 = new queues();			//testing member functions of queues
		Q1.insert(1);
		Q1.insert(2);
		Q1.insert(3);
		Q1.insert(4);
		Q1.insert(5);
		System.out.println(Q1.get_first());
		System.out.println("\n");

		Q1.remove();
		Q1.remove();
		System.out.println(Q1.get_first());
		System.out.println("\n");

		queues Q2 = Q1;
		System.out.println(Q2.get_first());
		System.out.println();
		
	}

}

   

