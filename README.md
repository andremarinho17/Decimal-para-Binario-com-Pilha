# Decimal para Binario com Pilha em Java  
Código que converte um número decimal qualquer para um número binário \n

//Classe Pilha

public class Pilha {
    private int valores[];
    private int topo;
    
    public Pilha(){
        valores = new int[10];
        topo = -1;
    }
    
    public void Push(int elemento){
        topo = topo + 1;
        valores[topo] = elemento;
    }
    
    public boolean isEmpty(){
        return (topo == -1);
    }
       
    
    public boolean isFull(){
        return (topo == 9);
        
    }
    
    public int pop(){
        int elem = valores[topo];
        topo--;
        return elem;
    }

}

// Classe DecimalToBinary

public class DecimalToBinary {

 
    public static void main(String[] args) {

        
        int numero = 172, resto;
        Pilha p = new Pilha();
        
        
        // fase 1 = empilhamento dos restos
        while(numero != 0){
            resto = numero % 2;  //pego o resto da divisão deste numero por 2
            p.Push(resto); //armazeno na pilha
            numero = numero/2;
        }
        
        // fase 2 = exibição dos restos
        while(!p.isEmpty()){
            resto = p.pop();  // remove da pilha(sempre o cara que está no topo)
            System.out.print(resto);
        }
        
        System.out.println("\n fim do programa");
    }
    
}
