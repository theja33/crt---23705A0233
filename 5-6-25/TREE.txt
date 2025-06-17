public class Main{
    public static void main(String[] args){
        Tree t=new Tree(new int[] {1,2,4,-1,-1,5,7,-1,8,-1,-1,-1,3,9,11,-1,-1,10,-1,-1,-1});
        Node root= t.getRoot();
        int heightOfRoot=Tree.heightOf(root);
        System.out.println("height of tree is:"+heightOfRoot);
    }
}
class Tree{
    Node root;
    int index=-1;
    Tree(int[] nodes){
        this.root=buildTreeUsingArray(nodes);
        System.out.println(index);
    }
public Node buildTreeUsingArray(int[] nodes){
    index++;
    if(index>= nodes.length){
        return null;
    }
    if(nodes[index]==-1)
     return null;
     Node newNode = new Node(nodes[index]);
     newNode.left=buildTreeUsingArray(nodes);
     newNode.right=buildTreeUsingArray(nodes);
     return newNode;
}
Node getRoot(){
    return root;
}
public static int heightOf(Node root){
    if(root == null) return 0;
    int lh = heightOf(root.left);
    int rh=heightOf(root.right);
    return Math.max(lh,rh)+1;
}
}
class Node{
    int data;
    Node left;
    Node right;
    Node(int data){
        this.data=data;
        this.left=null;
        this.right=null;
    }
}
