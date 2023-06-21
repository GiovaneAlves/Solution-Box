# Solution-Box

- __Projeto A3:__  Propor um software para desenvolvimento dos conhecimentos já aprendindas até aqui sobre técnicas de engenharia de software.
-----
- ### __Quem Somos:__ 

__Solution Box__ é uma empresa inovadora especializada em software de caixa automatizado. Nossa solução revoluciona o processo de operação de caixas, eliminando a necessidade de intervenção humana. Com nosso software avançado e intuitivo, os clientes podem realizar transações de forma rápida e eficiente, sem a necessidade de um operador. Através de uma interface fácil de usar, o software da Solution Box gerencia pagamentos.

---
- ### __Logo:__ 
![Logo da empresa](image/logo%20solution%20box.jpeg)

______
- ### __Time Scrum:__

__Scrum Master:__ Giovane (Dev. Sênior)

__Product Owner:__ Camila (Engenheira de Software)

__Equipe de Desenvolvimento:__ - Maria Eduarda (Analista de Requisitos) - Marcelo (Dev Pleno) - Erick (Dev Junior) - Kollins (Dev Pleno)

___
- ### __Stackholders:__

Giovane (Dev Sênior)

Camila (Engenheira de Software)

Maria Eduarda (Analista de Requisitos)

Rafael (Gerente Supermecado)

Talita (Chefe de Caixa)

____
- ### __Levantamento de Requisitos:__
A técnica escolhida para o levantamento de requisitos será o seminário. Essa técnica é adequada quando é necessário envolver um grande número de stakeholders e promover uma interação colaborativa entre eles.
Neste caso, o seminário será conduzido com a participação dos seguintes stakeholders:

•	Giovane, que é um Dev Sênior experiente, trará sua expertise técnica para auxiliar nas discussões e garantir que os requisitos sejam viáveis do ponto de vista do desenvolvimento do software.

•	Camila, como Engenheira de Software, trará sua experiência na área para contribuir com insights sobre a arquitetura do sistema, as possibilidades tecnológicas e as melhores práticas a serem consideradas durante o levantamento de requisitos.

•	Maria Eduarda, como Analista de Requisitos, desempenhará um papel fundamental na organização e facilitação do seminário. Ela será responsável por orientar as discussões, garantir a compreensão dos requisitos pelos participantes e registrar as informações relevantes.

•	Rafael, o Gerente do Supermercado, será convidado para trazer a perspectiva da gestão e os requisitos específicos do negócio. Sua contribuição ajudará a alinhar o software às necessidades e estratégias da empresa.

•	Talita, como Chefe de Caixa, trará sua experiência prática na operação de caixas e poderá compartilhar requisitos relacionados à eficiência do processo de pagamentos e às necessidades dos operadores de caixa.

Durante o seminário, cada stakeholder terá a oportunidade de compartilhar suas perspectivas, desafios e requisitos específicos relacionados ao software de caixa automatizado. A interação entre os participantes permitirá uma compreensão mais abrangente das necessidades do negócio, das limitações técnicas e das preferências dos usuários finais.

As apresentações preparadas por Camila e Maria Eduarda ajudarão a guiar as discussões, fornecendo informações relevantes sobre os requisitos técnicos e de negócio. Através dessas discussões, Giovane poderá contribuir com insights valiosos, garantindo a viabilidade técnica dos requisitos levantados.

Após o seminário, Maria Eduarda consolidará as informações registradas durante as discussões e buscará validação dos requisitos junto aos participantes. Esse processo de validação permitirá confirmar a precisão e relevância dos requisitos levantados e fornecerá uma base sólida para o desenvolvimento do software de caixa automatizado, atendendo às expectativas e necessidades dos stakeholders envolvidos.
___
- ### Backlog do Produto:__
Sprint 1:

US1: Como cliente, desejo poder realizar pagamentos utilizando o software da Solution Box. (Tamanho: Pequeno, Prioridade: Alta)

US2: Como cliente, desejo ter uma interface intuitiva que facilite a realização de transações. (Tamanho: Médio, Prioridade: Alta)

Sprint 2:

US3: Como cliente, desejo poder registrar os detalhes das transações realizadas. (Tamanho: Médio, Prioridade: Alta)

US4: Como cliente, desejo ter um histórico de transações para fins de referência. (Tamanho: Pequeno, Prioridade: Média)

Sprint 3:

US5: Como cliente, desejo ter a opção de receber recibos eletrônicos após cada transação. (Tamanho: Pequeno, Prioridade: Média)

US6: Como administrador, desejo ter acesso a relatórios de vendas para análise de desempenho. (Tamanho: Grande, Prioridade: Alta)

Sprint 4:

US7: Como cliente, desejo poder realizar transações com diferentes métodos de pagamento (cartão de crédito, dinheiro, etc.). (Tamanho: Grande, Prioridade: Alta)

US8: Como administrador, desejo poder configurar diferentes níveis de acesso para os usuários do software. (Tamanho: Médio, Prioridade: Média)

Sprint 5:

US9: Como cliente, desejo ter a opção de dividir o pagamento em várias parcelas. (Tamanho: Grande, Prioridade: Média)

US10: Como administrador, desejo receber notificações de transações bem-sucedidas ou problemas de pagamento. (Tamanho: Pequeno, Prioridade: Alta)


![Alt text](image/trello%20baclog.png)
___

![Alt text](image/Diagrama%20de%20Classe.png)
____
- ### __Protótipo Interface:__

__Tela 01 - Login__
![Alt text](image/login.jpg)

__Tela 02 - Leitor Código de Barras__
![Alt text](image/leitor_codigo_barras.jpg)

__Tela 03 - Carrinho de Compras__
![Alt text](image/carrinho_compras.jpg)

__Tela 04 - Pagamento__
![Alt text](image/pagamento.jpg)

__Tela 05 - Confirmação__
![Alt text](image/confirmacao.jpg)
___
- ### __Código Fonte:__
```
class TransacaoFactory:
    def criarTransacao(self):
        pass


class VendaTransacaoFactory(TransacaoFactory):
    def criarTransacao(self):
        return VendaTransacao()


class Transacao:
    def registrarDetalhes(self):
        pass

    def realizarPagamento(self):
        pass

    def enviarReciboEletronico(self):
        pass

    def getValorTotal(self):
        pass


class VendaTransacao(Transacao):
    # Implementação da classe VendaTransacao
    pass


class Produto:
    def __init__(self, codigo, nomeProduto, preco):
        self.codigo = codigo
        self.nomeProduto = nomeProduto
        self.preco = preco

    def getCodigo(self):
        return self.codigo

    def getNomeProduto(self):
        return self.nomeProduto

    def getPreco(self):
        return self.preco


class CaixaAutomatizado:
    def __init__(self, codigo, bancoDeDadosProdutos, transacaoFactory):
        self.codigo = codigo
        self.status = "Fechado"
        self.valorTotal = 0.0
        self.historicoTransacoes = []
        self.bancoDeDadosProdutos = bancoDeDadosProdutos
        self.estoque = {}
        self.transacaoFactory = transacaoFactory

    def abrirCaixa(self):
        self.status = "Aberto"

    def fecharCaixa(self):
        self.status = "Fechado"

    def registrarTransacao(self, transacao, valorTotal):
        self.historicoTransacoes.append(transacao)
        self.valorTotal += valorTotal

    def gerarRelatorioVendas(self):
        # Implementação da geração de relatório de vendas
        pass

    def imprimirReciboEletronico(self, transacao):
        # Implementação da impressão do recibo eletrônico da transação
        pass

    def atualizarEstoque(self, produto, quantidade):
        # Implementação da atualização do estoque após a transação
        pass

    def existeProduto(self, codigoBarras):
        # Implemente a lógica para verificar a existência do produto no banco de dados externo
        pass

    def getProduto(self, codigoBarras):
        # Implemente a lógica para obter o produto pelo código de barras do banco de dados externo
        pass

    def getQuantidadeEstoque(self, produto):
        # Implemente a lógica para obter a quantidade em estoque do produto do banco de dados externo
        pass

    def registrarTransacaoDeVenda(self, codigosBarras):
        valorTotalVenda = 0.0

        for codigoBarras in codigosBarras:
            if self.existeProduto(codigoBarras):
                produto = self.getProduto(codigoBarras)
                quantidadeEstoque = self.getQuantidadeEstoque(produto)

                if quantidadeEstoque > 0:
                    valorTotalVenda += produto.getPreco()
                    self.atualizarEstoque(produto, quantidadeEstoque - 1)
                else:
                    print("Produto", produto.getNomeProduto(), "fora de estoque.")
            else:
                print("Produto não encontrado no banco de dados.")

        transacao = self.transacaoFactory.criarTransacao()
        self.historicoTransacoes.append(transacao)
        self.valorTotal += valorTotalVenda


if __name__ == "__main__":
    bancoDeDadosProdutos = {}
    # Adicione os produtos ao banco de dados

    transacaoFactory = VendaTransacaoFactory()
    caixa = CaixaAutomatizado("CA001", bancoDeDadosProdutos, transacaoFactory)

    caixa.abrirCaixa()

    codigosBarras = ["0001", "0002", "0003"]
    caixa.registrarTransacaoDeVenda(codigosBarras)

    caixa.fecharCaixa()
```
___
- ### __Padrão de Projeto:__
[Padrão de Projeto Solution Box - Factory Method](doc/Padr%C3%A3o%20de%20Projeto%20Factory%20Method.pdf)


