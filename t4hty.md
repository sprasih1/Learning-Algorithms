import java.lang.*;
import java.io.*;
import java.util.*;
class Node{
    int d;
    Node left;
    Node right;
    Node(int d){
        this.d =d;
        this.left = null;
        this.right = null;
    }
}
class GFG {
    Node root;
    GFG(){
        root = null;
    }
    public int size(Node x){
        if(x==null)
            return 0;
        else
            return 1+size(x.left)+size(x.right);
    }
    public int rank(Node x,int d){
        //System.out.print("d is "+d);
        if(x==null){
            return 0;
        }
        if(x.d==d){
            //System.out.print("size1 is "+size(x.left));
            if(x.left==null)
                return 0;
            else 
                return size(x.left);
        }
        else if(d<x.d){
            return rank(x.left,d);
        }
        else{
            if(x.right==null)
                return 0;
            else
                return 1+size(x.left)+rank(x.right,d);
        }
    }
    public Node insert(Node x,int d){
        
        if(x==null){
            Node n = new Node(d);
            return n;
        }
        else if(d>=x.d){
            x.right = insert(x.right,d);
        }
        else if(d<x.d){
            x.left = insert(x.left,d);
        }
        return x;
    }
    public void countSmaller(int a[],int n){
        int[] res = new int[n];
        res[n-1] = 0;//adding 0 for the rightmost element.
        root = insert(root,a[n-1]);
        for(int i=n-2;i>=0;i--){
            root = insert(root,a[i]);
            res[i] = rank(root,a[i]);
        }
        for(int i=0;i<n;i++){
            System.out.print(res[i]+" ");
        }
        System.out.println();
    }
	public static void main (String[] args) {
	    
	    Scanner in = new Scanner(System.in);
	    int t = in.nextInt();
	    for(int i=0;i<t;i++){
	        int n = in.nextInt();
	        int a[] = new int[n];
	        for(int j=0;j<n;j++){
	            a[j] = in.nextInt();
	            
	        }
	        GFG g = new GFG();
	        g.countSmaller(a,n);
	    }
	}
}
