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
