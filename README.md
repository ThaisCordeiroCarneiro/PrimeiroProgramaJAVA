# PrimeiroProgramaJAVA
Trabalho Pratico da aula de JAVA do Bootcamp Programador de Software Iniciante IGTI.

Criando o primeiro repositorio.

// Criar um programa que pegue os dados das pessoas: nome, idade e situação (A,I,E);
//não permitir nomes vazios, idades negativas, situações diferentes das definidas pelo sistema;
//Ao final, exibir: todos os dados das pessoas / a que tem a maior idade / o total de pessoas em cada situação;
		

package pacotePratica30_08;
import java.util.Scanner;

public class ClassePratica30_08 {

private static Scanner entCaracter;
private static Scanner entNumero;

public static void main(String[] args) {
	
		String[]nome = new String [50];
		int [] idade = new int [50];
		char[] situacao = new char [50];
		
		char continuar = 'S';
		int nPessoas = 0;
		int maiorIdade = 0;
		int totSituacaoA = 0,totSituacaoI = 0,totSituacaoE = 0; 
		
		entCaracter = new Scanner (System.in);
		entNumero = new Scanner (System.in);
		
		while (continuar == 'S' || continuar == 's'){
			System.out.printf("Digite o nome da %da.pessoa: \n", nPessoas+1);
			nome[nPessoas] = entCaracter.nextLine();
			
				while (nome[nPessoas].equals(" ") || nome[nPessoas] ==null) {
					System.out.printf("Nome Invalido. Digite novamente o nome da %da.pessoa: \n", nPessoas+1);
				}
				
			System.out.printf("Digite a idade da %da. pessoas: \n", nPessoas+1);
			idade[nPessoas] = entNumero.nextInt();
			
				while (idade[nPessoas] < 0) {
					System.out.printf("Idade Iválida.Digitenovamente a idade da %da.pessoa: \n", nPessoas+1);
				}
					if (idade[nPessoas] > maiorIdade)
						maiorIdade = idade[nPessoas] + 1;
			
			System.out.printf("Digite a situação da %da.pessoa: (A-ativa; I-inativo; E-excluido): \n", nPessoas+1);
			situacao[nPessoas] = entCaracter.nextLine().charAt(0);
			
				while( situacao[nPessoas] != 'A' || situacao[nPessoas] != 'a' &&
					   situacao[nPessoas] != 'I' || situacao[nPessoas] != 'i' &&
					   situacao[nPessoas] != 'E' || situacao[nPessoas] != 'e'){
					System.out.printf("Situação Invalida. Digite novamente a situação da %da.pessoa: \n", nPessoas+1);
				}
					if (situacao[nPessoas] == 'A' || situacao[nPessoas] == 'a')
							totSituacaoA = situacao[nPessoas] + 1;
					else if (situacao[nPessoas] == 'I' || situacao[nPessoas] == 'i')
						totSituacaoI = situacao[nPessoas] + 1;
					else if (situacao[nPessoas] == 'E' || situacao[nPessoas] == 'e')
						totSituacaoE = situacao[nPessoas] + 1;
		
		
			System.out.println("Deseja Continuar: 'S'-sim ou 'N'-não?");
			continuar = entCaracter.nextLine().charAt(0);
			
			nPessoas = nPessoas +1;
		}

		System.out.println("------DADOS DAS PESSOAS------");
		for (int i=0; i<nPessoas; i++) {
			System.out.printf("Nome: %s. Idade: %d. Situação: %c \n", nome[i], idade[i], situacao[i]);
			System.out.printf("A maior idade encontrada foi na %da.pessoa", nome[i],nPessoas);
			System.out.printf("Total de pessoas por situação: A: %d; I: %d; E: %d \n",totSituacaoA, totSituacaoI, totSituacaoE);
		}
}
}
