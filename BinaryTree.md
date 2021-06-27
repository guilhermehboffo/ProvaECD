### Unipar - Universidade Paranaense - Curso de Análise e Desenvolvimento de Sistemas - 2° Série

Aluno: Guilherme Henrique Boffo <br/>
RA: 00211995

Professor: Geferson Luis Simonette <br/>
Matéria: Estrutura e classificação de dados

---

# Árvore binária

As árvores são estruturas de dados baseadas em listas encadeadas que possuem um nó superior também chamado
de raiz que aponta para outros nós, chamados de nós filhos, que podem ser pais de outros nós.

Uma árvore de busca binária tem as seguintes propriedades:

- Todos os elementos na subárvore esquerda de um determinado nó n são menores que n.
- Todos os elementos na subárvore direita de um determinado nó n são maiores ou iguais a n.

Como por exemplo:

![ÁrvoreBináriaEx](https://arquivo.devmedia.com.br/artigos/Higor_Medeiros/ArvoreBinaria/ArvoreBinaria1.jpg)

No exemplo acima tem-se uma árvore binária onde a raiz é o elemento 8, o filho da esquerda do elemento 8 é o 
elemento 3, o filho da direita é o elemento número 10. Nota-se que todos elementos da árvore binária possuem 
no máximo dois filhos, sendo o da esquerda sempre menor e o da direita sempre maior que o elemento pai.

## Exemplo de implementação da Árvore Binária
### Algoritmos para inserção e exclusão em árvores binárias implementados na linguagem Java.

```
public void inserir(No node, int valor) {
  //verifica se a árvore já foi criada
   if (node != null) {
    //Verifica se o valor a ser inserido é menor que o nodo corrente da árvore, se sim vai para subárvore esquerda
    if (valor < node.valor) {
        //Se tiver elemento no nodo esquerdo continua a busca
        if (node.esquerda != null) {
            inserir(node.esquerda, valor);
        } else {
            //Se nodo esquerdo vazio insere o novo nodo aqui
            System.out.println("  Inserindo " + valor + " a esquerda de " + node.valor);
            node.esquerda = new No(valor);
        }
    //Verifica se o valor a ser inserido é maior que o nodo corrente da árvore, se sim vai para subárvore direita
    } else if (valor > node.valor) {
        //Se tiver elemento no nodo direito continua a busca
        if (node.direita != null) {
            inserir(node.direita, valor);
        } else {
            //Se nodo direito vazio insere o novo nodo aqui
            System.out.println("  Inserindo " + valor + " a direita de " + node.valor);
            node.direita = new No(valor);
        }
    }
  }
}
```
O algoritmo mostrado acima funciona de forma recursiva chamando a função repetidas vezes, o próximo algoritmo
a ser mostrado trata-se de algoritmo alternativo para exclusão em árvores binárias.

```
public No removeValorMinimoDaArvore(No node) {
    if (node == null) {
        System.out.println("  ERRO ");
    } else if (node.esquerda != null) {
        node.esquerda = removeValorMinimoDaArvore(node.esquerda);
        return node;
    } else {
      //Se não tiver elemento esquerdo só nos resta o da direita
        return node.direita;
    }
    return null;
}
```
No código acima nota-se que o menor elemento da árvore está sendo excluído, o código também poderia ser 
implementado recebendo um nó a ser excluído, procurar este nó e excluir da árvore.

## Comparação do desempenho de uma Árvore Binária Balanceada e outra não balanceada

Uma árvore binária balanceada é aquela em que nenhum nó está "muito longe" da raiz. Por exemplo, uma 
definição de balanceada pode exigir que todos os nós tenham uma profundidade que difira no máximo em 1. 
Uma árvore binária desbalanceada, como seu próprio nome ja sugere, é uma árvore que não possui esse
mesmo balançeamento da primeira, uma árvore binária completa possui todos os níveis completamente 
preenchidos, exceto pelo último em alguns casos. Se uma árvore completa tem profundidade máxima n, 
então ela tem pelo menos 2n e no máximo 2n + 1−1 nós. Uma árvore completa com exatamente 2n + 1−1 nós
é chamada de perfeita. <br/>

### Balanceada:
![ÁrvoreBináriaBalanceadaEx](https://people.orie.cornell.edu/snp32/orie_6125/_images/bst.png)

### Desalanceada:
![ÁrvoreBináriaDesbalanceadaEx](https://people.orie.cornell.edu/snp32/orie_6125/_images/unbalanced_tree.png)

Uma árvore binária de busca depende da ordem da inserção para ter um tempo assintótico de busca ótimo,
visto que o primeiro valor inserido será usado como uma raiz e os demais irão para esquerda ou para 
direita se forem maiores ou menores. Sendo assim se vc adicionar os valores em ordem crescente de s 
ficarão todos a direita do valor anterior, logo o tempo de busca será de O(n), sendo n o número de valores. <br/>
Já em uma árvore AVL isso não ocorre pois cada valor na árvore possui um dado que determina seu 
balanceamento baseado na altura do seu nó a direita menos a altura do seu nó a esquerda, lembrando que 
esses valores podem ser -1=<FB<=1. <br/>
Caso, após uma inserção qualquer valor da árvore fique com um fator de balanceamento diferente desses
valores, a arvore se reestrutura mudando suas ligações para que todos os seu nós tenha esse fator de
balanceamento. Sendo assim o tempo de busca assintótico ficará em torno de O(Log2n) independente da ordem de 
inserção dos valores.

## Exemplo Prático Árvore AVL

```
    /*

     *  Java Program to Implement AVL Tree

     */

     

     import java.util.Scanner;

     

     /* Class AVLNode */

     class AVLNode

     {    

         AVLNode left, right;

         int data;

         int height;

     

         /* Constructor */

         public AVLNode()

         {

             left = null;

             right = null;

             data = 0;

             height = 0;

         }

         /* Constructor */

         public AVLNode(int n)

         {

             left = null;

             right = null;

             data = n;

             height = 0;

         }     

     }

     

     /* Class AVLTree */

     class AVLTree

     {

         private AVLNode root;     

     

         /* Constructor */

         public AVLTree()

         {

             root = null;

         }

         /* Function to check if tree is empty */

         public boolean isEmpty()

         {

             return root == null;

         }

         /* Make the tree logically empty */

         public void makeEmpty()

         {

             root = null;

         }

         /* Function to insert data */

         public void insert(int data)

         {

             root = insert(data, root);

         }

         /* Function to get height of node */

         private int height(AVLNode t )

         {

             return t == null ? -1 : t.height;

         }

         /* Function to max of left/right node */

         private int max(int lhs, int rhs)

         {

             return lhs > rhs ? lhs : rhs;

         }

         /* Function to insert data recursively */

         private AVLNode insert(int x, AVLNode t)

         {

             if (t == null)

                 t = new AVLNode(x);

             else if (x < t.data)

             {

                 t.left = insert( x, t.left );

                 if( height( t.left ) - height( t.right ) == 2 )

                     if( x < t.left.data )

                         t = rotateWithLeftChild( t );

                     else

                         t = doubleWithLeftChild( t );

             }

             else if( x > t.data )

             {

                 t.right = insert( x, t.right );

                 if( height( t.right ) - height( t.left ) == 2 )

                     if( x > t.right.data)

                         t = rotateWithRightChild( t );

                     else

                         t = doubleWithRightChild( t );

             }

             else

               ;  // Duplicate; do nothing

             t.height = max( height( t.left ), height( t.right ) ) + 1;

             return t;

         }

         /* Rotate binary tree node with left child */     

         private AVLNode rotateWithLeftChild(AVLNode k2)

         {

             AVLNode k1 = k2.left;

             k2.left = k1.right;

             k1.right = k2;

             k2.height = max( height( k2.left ), height( k2.right ) ) + 1;

             k1.height = max( height( k1.left ), k2.height ) + 1;

             return k1;

         }

     

         /* Rotate binary tree node with right child */

         private AVLNode rotateWithRightChild(AVLNode k1)

         {

             AVLNode k2 = k1.right;

             k1.right = k2.left;

             k2.left = k1;

             k1.height = max( height( k1.left ), height( k1.right ) ) + 1;

             k2.height = max( height( k2.right ), k1.height ) + 1;

             return k2;

         }

         /**

          * Double rotate binary tree node: first left child

          * with its right child; then node k3 with new left child */

         private AVLNode doubleWithLeftChild(AVLNode k3)

         {

             k3.left = rotateWithRightChild( k3.left );

             return rotateWithLeftChild( k3 );

         }

         /**

          * Double rotate binary tree node: first right child

          * with its left child; then node k1 with new right child */      

         private AVLNode doubleWithRightChild(AVLNode k1)

         {

             k1.right = rotateWithLeftChild( k1.right );

             return rotateWithRightChild( k1 );

         }    

         /* Functions to count number of nodes */

         public int countNodes()

         {

             return countNodes(root);

         }

         private int countNodes(AVLNode r)

         {

             if (r == null)

                 return 0;

             else

             {

                 int l = 1;

                 l += countNodes(r.left);

                 l += countNodes(r.right);

                 return l;

             }

         }

         /* Functions to search for an element */

         public boolean search(int val)

         {

             return search(root, val);

         }

         private boolean search(AVLNode r, int val)

         {

             boolean found = false;

             while ((r != null) && !found)

             {

                 int rval = r.data;

                 if (val < rval)

                     r = r.left;

                 else if (val > rval)

                     r = r.right;

                 else

                 {

                     found = true;

                     break;

                 }

                 found = search(r, val);

             }

             return found;

         }

         /* Function for inorder traversal */

         public void inorder()

         {

             inorder(root);

         }

         private void inorder(AVLNode r)

         {

             if (r != null)

             {

                 inorder(r.left);

                 System.out.print(r.data +" ");

                 inorder(r.right);

             }

         }

         /* Function for preorder traversal */

         public void preorder()

         {

             preorder(root);

         }

         private void preorder(AVLNode r)

         {

             if (r != null)

             {

                 System.out.print(r.data +" ");

                 preorder(r.left);             

                 preorder(r.right);

             }

         }

         /* Function for postorder traversal */

         public void postorder()

         {

             postorder(root);

         }

         private void postorder(AVLNode r)

         {

             if (r != null)

             {

                 postorder(r.left);             

                 postorder(r.right);

                 System.out.print(r.data +" ");

             }

         }     

     }

     

     /* Class AVL Tree Test */

     public class AVLTreeTest

     {

         public static void main(String[] args)

        {            

            Scanner scan = new Scanner(System.in);

            /* Creating object of AVLTree */

            AVLTree avlt = new AVLTree(); 

     

            System.out.println("AVLTree Tree Test\n");          

            char ch;

            /*  Perform tree operations  */

            do    

            {

                System.out.println("\nAVLTree Operations\n");

                System.out.println("1. insert ");

                System.out.println("2. search");

                System.out.println("3. count nodes");

                System.out.println("4. check empty");

                System.out.println("5. clear tree");

     

                int choice = scan.nextInt();            

                switch (choice)

                {

                case 1 : 

                    System.out.println("Enter integer element to insert");

                    avlt.insert( scan.nextInt() );                     

                    break;                          

                case 2 : 

                    System.out.println("Enter integer element to search");

                    System.out.println("Search result : "+ avlt.search( scan.nextInt() ));

                    break;                                          

                case 3 : 

                    System.out.println("Nodes = "+ avlt.countNodes());

                    break;     

                case 4 : 

                    System.out.println("Empty status = "+ avlt.isEmpty());

                    break;     

                case 5 : 

                    System.out.println("\nTree Cleared");

                    avlt.makeEmpty();

                    break;         

                default : 

                    System.out.println("Wrong Entry \n ");

                    break;   

                }

                /*  Display tree  */ 

                System.out.print("\nPost order : ");

                avlt.postorder();

                System.out.print("\nPre order : ");

                avlt.preorder();

                System.out.print("\nIn order : ");

                avlt.inorder();

     

                System.out.println("\nDo you want to continue (Type y or n) \n");

                ch = scan.next().charAt(0);                        

            } while (ch == 'Y'|| ch == 'y');               

        }

     }
```
Ref: https://www.devmedia.com.br/trabalhando-com-arvores-binarias-em-java/25749 <br/> 
https://people.orie.cornell.edu/snp32/orie_6125/data-structures/binary-tree.html <br/> 
https://brainly.com.br/tarefa/5275484 <br/>
https://www.sanfoundry.com/java-program-implement-avl-tree/
