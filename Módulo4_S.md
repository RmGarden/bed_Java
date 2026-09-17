´´´Java
import java.util.Scanner;

// Classe que representa o objeto na Heap
class Cofre {
    private String nome;
    private int valor;
    private boolean trancado;

    public Cofre(String nome, int valor) {
        this.nome = nome;
        this.valor = valor;
        this.trancado = true;
    }

    public String getNome() { return nome; }
    public int getValor() { return valor; }
    public boolean isTrancado() { return trancado; }

    public void injetarMoedas(int quantia) {
        this.valor += quantia;
    }

    public void hackearFechadura() {
        this.trancado = false;
    }
}

public class HackerDaHeap {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Instanciação dos objetos na memória Heap
        Cofre cofreA = new Cofre("Cofre Alpha", 1000);
        Cofre cofreB = new Cofre("Cofre Beta", 5000);
        Cofre cofreC = new Cofre("Cofre Central", 99999);

        // Variável de REFERÊNCIA (funciona como o "ponteiro" do Java)
        Cofre alvoAtual = null;

        boolean jogoAtivo = true;

        while (jogoAtivo) {
            // Limpar ecrã no terminal
            System.out.print("\033[H\033[2J");
            System.out.flush();

            System.out.println("====================================================");
            System.out.println(" ☕ HACKER DA HEAP: INSPEÇÃO DE REFERÊNCIAS JAVA   ");
            System.out.println("====================================================");
            System.out.println(" 1. " + cofreA.getNome() + " | Valor: " + cofreA.getValor() + " | Trancado: " + cofreA.isTrancado());
            System.out.println(" 2. " + cofreB.getNome() + " | Valor: " + cofreB.getValor() + " | Trancado: " + cofreB.isTrancado());
            System.out.println(" 3. " + cofreC.getNome() + " | Valor: " + cofreC.getValor() + " | Trancado: " + cofreC.isTrancado());
            System.out.println("====================================================\n");

            if (alvoAtual != null) {
                System.out.println("🎯 REFERÊNCIA ATUAL CONECTADA A: " + alvoAtual.getNome());
                System.out.println("💎 VALOR DO OBJETO CONECTADO: " + alvoAtual.getValor() + "\n");
            } else {
                System.out.println("⚠️ NENHUM OBJETO CONECTADO (alvoAtual == null)!\n");
            }

            System.out.println("O que queres fazer?");
            System.out.println("1. Apontar referência para o Cofre Alpha");
            System.out.println("2. Apontar referência para o Cofre Beta");
            System.out.println("3. Apontar referência para o Cofre Central");
            System.out.println("4. 🔓 Injetar valor no Cofre atualmente conectado");
            System.out.println("5. 🛠️ Hackear fechadura do Cofre conectado");
            System.out.println("6. 🚪 Sair do Sistema");
            System.out.print("Escolha: ");

            int escolha = scanner.nextInt();

            switch (escolha) {
                case 1:
                    alvoAtual = cofreA; // Guarda a referência de cofreA
                    break;
                case 2:
                    alvoAtual = cofreB; // Guarda a referência de cofreB
                    break;
                case 3:
                    alvoAtual = cofreC; // Guarda a referência de cofreC
                    break;
                case 4:
                    if (alvoAtual == null) {
                        System.out.println("\n❌ Erro! Não podes alterar um objeto NULO (NullPointerException)!");
                    } else {
                        System.out.print("\nQuantia a injetar na Heap: ");
                        int quantia = scanner.nextInt();
                        alvoAtual.injetarMoedas(quantia);
                        System.out.println("\n✨ Sucesso! Objeto modificado na Heap via referência.");
                    }
                    break;
                case 5:
                    if (alvoAtual == null) {
                        System.out.println("\n❌ Erro! Nenhum alvo selecionado.");
                    } else {
                        alvoAtual.hackearFechadura();
                        System.out.println("\n🔓 Fechadura do objeto alterada com sucesso!");
                    }
                    break;
                case 6:
                    System.out.println("\nA desligar o terminal...");
                    jogoAtivo = false;
                    break;
                default:
                    System.out.println("\nOpção inválida!");
            }

            if (jogoAtivo) {
                System.out.println("\nPressiona Enter para continuar...");
                scanner.nextLine();
                scanner.nextLine();
            }
        }
        scanner.close();
    }
}
