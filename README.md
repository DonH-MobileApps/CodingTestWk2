# CodingTestWk2
Source Code P. 2


package com.example.codingtestwk2;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;

import java.util.Stack;




//  problem 2 source code
public class MainActivity extends AppCompatActivity {


    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }


    static class Queue {
        static Stack<Integer> s1 = new Stack<Integer>();
        static Stack<Integer> s2 = new Stack<Integer>();

        static void enQueue(int x) {

            while (!s1.isEmpty()) {
                s2.push(s1.pop());

            }


            s1.push(x);


            while (!s2.isEmpty()) {
                s1.push(s2.pop());

            }
        }


        static int deQueue() {

            if (s1.isEmpty()) {
                System.out.println("Q is Empty");
                System.exit(0);
            }

            int x = s1.peek();
            s1.pop();
            return x;
        }
    }


    public static void main(String[] args) {
        Queue q = new Queue();
        q.enQueue(1);
        q.enQueue(2);
        q.enQueue(3);
        q.enQueue(4);
        q.enQueue(5);

        System.out.println(q.deQueue());
        System.out.println(q.deQueue());
        System.out.println(q.deQueue());
        System.out.println(q.deQueue());
        System.out.println(q.deQueue());
    }





}

 /* *************************************

        1
        2
        3
        4
        5

        Process finished with exit code 0

 *********************************************/
