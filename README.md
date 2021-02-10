# Teste_intelitrader
Teste para vaga

Caixa eletronico
https://dojopuzzles.com/problems/caixa-eletronico/


import java.util.Scanner;
import java.text.DecimalFormat;
import java.util.InputMismatchException;

public class caixaEletronico {

public static void main(String[] args) {
	Scanner ler = new Scanner(System.in);
    
	double valor;
	double vrl = 0;
	try{
	    System.out.println(" Digite o valor para sacar R$ ");
	    valor = ler.nextDouble();
	    
	    System.out.printf("%s", CalcularNota(valor,vrl));
	}
	catch(InputMismatchException e){
	    System.err.printf("\nErro:Erro dados informado\n");
	}
}
public static String CalcularNota(double valor, double vrl){
    DecimalFormat formatador = new DecimalFormat("###,##,00");
    if(valor <=5.00){
        return("Não há cédulas de R$5,00 no Caixa, por favor retorne a transação, e digite um valor maior que R$5,00\n");
        
    }
    else{
    	
        int nota[]={100,50,20,10};
        
        
        	String result;
	        double tr;
		    int i,ct,vlr;
		    tr = valor - vrl;
		    result = "\n Valor R$ " + tr + "\n\n";
		    vlr = (int)tr;
		    i = 0;
		    while(vlr != 0){
		        ct = vlr/nota[i];
		        if(ct!=0){
		            result=result + (ct + "nota(s) de R$ "+ nota[i] + "\n");
		            vlr = vlr % nota[i];
		        }
		        i = i + 1;
		    }
		    return(result);    	
    }
}




Teste 2 - FizzBuzz

class FizzBuzz{

    public static void main(String args[]){
        for (int x = 1; x <= 100; x++){
            if ((x % 3 == 0) && (x % 5 == 0)){
                System.out.println("FizzBuzz");
            } else if(x % 3 == 0){
                System.out.println("Fizz");
            } else if(x % 5 == 0){
                System.out.println("Buzz");
            } else {
                System.out.println(x);
            }
        }
    }

}



Teste 3 - Jokenpo

import java.util.Scanner;

class Jokenpo {
        public static void main (String args []){
		
		Scanner sc = new Scanner(System.in);
		int v1,v2;
		
		System.out.println("Escolha entre 0, 1 e 2 , sendo : ");
		System.out.println("Pedra = 0 ");
		System.out.println("Papel = 1  ");
		System.out.println("Tesoura = 2");
		
		System.out.println("Jogador 1: ");
		v1 = sc.nextInt();
		
		System.out.println("Jogador 2: ");
		v2 = sc.nextInt();
		
		switch (v1){
			case 0: 
				switch (v2){
					case 0:
						System.out.println("Empate");
						break;
					case 1:
						System.out.println("Jogador 2 ganhou");
						break;
					case 2:
						System.out.println("Jogador 1 ganhou");
						break;
						default: 
							System.out.println ("USUARIO BURRO DO CARALHO");
				} break;
			case 1:
				switch(v2) {
					case 0: 
						System.out.println("Jogador 1 ganhou");
						break;
					case 1:
						System.out.println(" Empatou");
						break;
					case 2:
						System.out.println("Jogador 2 ganhou");
						break;
					default: 
						System.out.println ("USUARIO BURRO DO CARALHO");
				} break;
			case 2:
				switch(v2) {
						case 0:
							System.out.println("Jogador 2 ganhou");
							break;
						case 1:
							System.out.println("Jogador 1 ganhou");
							break;
						case 2:
							System.out.println("Empate");
							break;
						default: 
				            System.out.println ("USUARIO BURRO DO CARALHO");
				} break;
			default: 
				System.out.println ("USUARIO BURRO DO CARALHO");
		}
	}
}
