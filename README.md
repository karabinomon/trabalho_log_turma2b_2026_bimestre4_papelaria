Conversation Log
Leia os arquivos e traga um resumo agrupado por aulas

Segue o resumo dos materiais da Semana 25 — Do menu ao sistema completo (Unidade 6, Componente 1: Vetores e matrizes, projeto Papelaria Ponto Certo em Python), agrupado por aula:

Aula 1 — Enxergando o sistema por partes (SISANO1C1B4S25A1)
Arquivo: SISANO1C1B4S25A1ALUNO.pdf
Duração: 50 minutos
Objetivo: Analisar como sistemas em terminal articulam menu, funções, dados em memória e fluxo de execução.
Principais conceitos:
Arquitetura em 4 partes: Menu (apresenta opções) → Funções (executam tarefas) → Dados (listas em memória) → Fluxo (organiza a sequência até o Resultado).
Separação das listas: produtos armazena o catálogo atual (nome e preço) e vendas armazena o histórico de vendas realizadas (produto, quantidade e data). Cada função consulta a lista correspondente (ex.: listar_produtos usa produtos; classificar_desempenho() usa vendas).
Atividade prática (em duplas, 20 min): Refletir sobre o impacto de uma venda no histórico e mapear em uma tabela o percurso completo de uma venda pelo sistema (Menu → Registrar venda → produtos / vendas → Classificar desempenho).
Aula 2 — Quem faz o quê: dados e funções (SISANO1C1B4S25A2)
Arquivo: SISANO1C1B4S25A2ALUNO.pdf
Duração: 50 minutos
Objetivo: Analisar como distribuir responsabilidades entre funções e organizar dados em memória de forma coerente.
Principais conceitos:
Modularização: Dividir o programa em partes menores com responsabilidades claras (Menu coordena, Funções executam tarefas específicas, Dados mantêm listas em memória e Arquivo garante persistência).
Memória vs. Arquivo: Alterar a lista em memória resolve a execução atual; gravar o arquivo CSV (produtos.csv, vendas.csv) garante que a mudança permaneça nas próximas execuções.
Catálogo vs. Histórico: Não misturar alterações de produtos e vendas na mesma função.
Funções planejadas para o sistema: alterar_produto(), salvar_produtos(), registrar_venda(), cancelar_venda() e salvar_vendas().
Atividade prática (em duplas, 20 min): Analisar trechos de código em Python (atualização em memória e gravação em produtos.csv) e preencher uma tabela associando cada situação (alterar preço / cancelar venda) à função responsável, à lista modificada e ao arquivo gravado.
Aula 3 — Montando o minissistema (SISANO1C1B4S25A3)
Arquivos:
Slides: SISANO1C1B4S25A3ALUNO.pdf
Roteiro de Atividade Prática: SISANO1C1B4S25A3AP_ALUNO.docx
Duração: 50 minutos (42 min de prática)
Objetivo: Implementar as funcionalidades principais integrando menu, listas e validações básicas.
Atividade prática — Alterando produtos no sistema: Papelaria Ponto Certo:
Criar salvar_produtos(produtos) para gerar o produtos.csv inicial e carregar_produtos() para ler o CSV na abertura do programa.
Criar alterar_produto(produtos) para localizar o item pelo nome, solicitar novo nome (ou manter o atual) e novo preço, validar se o preço é numérico e não negativo, atualizar produtos em memória e chamar salvar_produtos(produtos).
Integrar a opção ao menu e testar: alteração válida, produto inexistente, preço inválido e persistência após fechar e reabrir o programa.
Aula 4 — Completando as opções do sistema (SISANO1C1B4S25A4)
Arquivos:
Slides: SISANO1C1B4S25A4ALUNO.pdf
Roteiro de Atividade Prática: SISANO1C1B4S25A4AP_ALUNO.docx
Duração: 50 minutos (47 min de prática)
Objetivo: Ampliar o sistema integrando as opções restantes do menu e os fluxos das aulas anteriores.
Atividade prática — Registrando e corrigindo vendas: Papelaria Ponto Certo:
Criar salvar_vendas(vendas) para gerar o vendas.csv inicial e carregar_vendas() para carregar o histórico na abertura do programa.
Criar registrar_venda(produtos, vendas) pedindo produto, quantidade e data — validando se o produto existe em produtos e se a quantidade é positiva —, adicionando à lista vendas e salvando em vendas.csv.
Criar cancelar_venda(vendas) exibindo os registros numerados, tratando lista vazia e número inválido, removendo o registro escolhido e regravando vendas.csv.
Ligar as duas opções ao menu, testar registros e cancelamentos válidos/inválidos, conferir persistência ao reabrir e entregar o código produzido no AVA.
Quero 6 questões de alternativas (a, b, c, d) com gabarito abaixo de cada questão

Segue abaixo uma lista com 6 questões de múltipla escolha baseadas nos conteúdos das Aulas 1 a 4 (Papelaria Ponto Certo), com o gabarito logo abaixo de cada uma:

1. No sistema da Papelaria Ponto Certo, o programa é organizado em quatro partes que trabalham juntas: Menu, Funções, Dados e Fluxo. Qual é o papel principal do Menu em um sistema modularizado?

a) Executar diretamente todas as alterações nas listas e gravar os arquivos CSV.
b) Substituir as listas em memória para que os dados não precisem ser carregados na abertura.
c) Apresentar as opções ao usuário e chamar a função responsável por cada ação.
d) Armazenar o histórico de vendas realizadas e o catálogo atual de produtos.

Gabarito: c) — Em um programa modularizado, o menu apenas coordena a interação com o usuário e chama a função específica encarregada de cada tarefa.

2. Após cadastrar o produto "Lápis" no sistema, o usuário consegue vê-lo ao consultar o catálogo, mas ao pedir a classificação de desempenho desse item, o programa informa "Sem histórico.". Por que isso acontece?

a) Porque o cadastro alterou apenas a lista produtos, enquanto a função classificar_desempenho() consulta a lista vendas.
b) Porque a função de consulta apagou o item recém-cadastrado da memória.
c) Porque o menu impediu o fluxo do programa de retornar às opções principais.
d) Porque produtos e vendas são a mesma lista e o Lápis foi salvo no índice errado.

Gabarito: a) — produtos guarda o catálogo atual e vendas guarda o histórico de vendas; cadastrar um item não registra nenhuma venda em vendas.

3. Qual é a diferença entre alterar um dado na lista em memória (como produto[1] = 19.90) e gravar o arquivo produtos.csv?

a) Alterar a lista em memória grava automaticamente no disco, dispensando o arquivo CSV.
b) A lista em memória vale apenas para a execução atual, enquanto gravar o arquivo CSV garante que a mudança continue disponível nas próximas execuções.
c) O arquivo CSV só serve para guardar o histórico de vendas, nunca o catálogo de produtos.
d) Gravar o arquivo CSV apaga os dados da lista em memória para liberar espaço antes de voltar ao menu.

Gabarito: b) — A lista em memória mantém os dados durante a execução em andamento; a gravação em arquivo CSV garante a persistência para quando o programa for fechado e reaberto.

4. Na implementação da função alterar_produto(produtos) (Aula 3), o que o programa deve fazer antes de atualizar a lista em memória e gravar o arquivo produtos.csv?

a) Apagar todos os registros de vendas.csv que tenham o mesmo nome do produto.
b) Chamar carregar_produtos() dentro do laço de repetição para reiniciar o catálogo.
c) Localizar o produto na lista e validar se o novo preço é numérico e não negativo.
d) Permitir que qualquer preço negativo seja salvo, corrigindo-o apenas na próxima abertura.

Gabarito: c) — Antes de alterar a lista e salvar no arquivo, a função deve localizar o item (tratando caso inexistente) e validar que o novo preço é numérico e maior ou igual a zero.

5. De acordo com o roteiro da Aula 4, ao criar a função registrar_venda(produtos, vendas), qual validação é obrigatória antes de incluir uma nova venda na lista vendas?

a) Verificar se a lista vendas está vazia para poder adicionar o primeiro item.
b) Garantir que o produto informado exista na lista produtos e que a quantidade seja um número positivo.
c) Exigir que o preço do produto seja alterado antes de concluir a venda.
d) Confirmar que a data da venda seja igual à data da última alteração em produtos.csv.

Gabarito: b) — Só se deve registrar uma venda se o produto estiver cadastrado no catálogo (produtos) e a quantidade informada for um número positivo.

6. Ao implementar cancelar_venda(vendas) e testar o sistema após fechar e reabrir o programa, um estudante percebe que a venda cancelada voltou a aparecer. Qual é a causa mais provável desse problema?

a) A função cancelar_venda(vendas) removeu o item da lista em memória, mas esqueceu de chamar salvar_vendas(vendas) (ou carregar_vendas() não foi chamada na abertura).
b) O menu chamou alterar_produto(produtos) em vez de listar_produtos().
c) A função cancelar_venda(vendas) exibiu os números dos registros na tela antes de pedir a escolha.
d) O arquivo produtos.csv não foi regravado logo após o cancelamento da venda.

Gabarito: a) — Para que o cancelamento persista após fechar e reabrir o sistema, é necessário remover o item de vendas, regravar vendas.csv com salvar_vendas(vendas) e carregar o arquivo na abertura com carregar_vendas().

Agora escreva em arquivo em .md com um passo a passo para implementar esse projeto, leve em consideração que o passo a passo são para iniciantes que tem conhecimento em estrutura básicas como while, for, input, print e variaveis, mas precisam de reforço com def e se a execução do não for um script tudão, se usar função main explique! O passo a passo deve iniciar de um construção lógica e não deve apresentar todo o código de uma unica vez, se preferencia faça pequenas modificações e antes de cada code-block formatado destaque no enunciado de cada bloco o que foi modifica ou se possivel deixe em negrito a parte nova do código dentro do code-block, se for usar lib externa descreva a crianção da venv usando o Visual Studio Code (não escreva a cli), eles já sabem fazer isso no Visual Studio Code

O arquivo passo_a_passo_papelaria.md foi criado na pasta do projeto com o roteiro incremental para iniciantes.

O que foi incluído no guia:
Sem venv necessária: explicado logo no início que o projeto usa apenas recursos nativos do Python (open() e os), dispensando bibliotecas externas.
Etapa 0 — Construção lógica: divisão do sistema em 4 partes (Menu, Funções, Dados em memória e Fluxo) e explicação didática sobre def, parâmetros e o papel da função main() com if __name__ == "__main__": para evitar um "script tudão".
Passos 1 a 7 (incrementais): evolução em pequenas modificações, destacando no enunciado de cada bloco o que foi alterado e marcando as linhas novas/modificadas com # NOVO / # MODIFICADO dentro dos blocos de código (para manter o Python válido ao copiar):
Esqueleto com mostrar_menu() e main()
listar_produtos(produtos) e classificar_desempenho(vendas)
Persistência em produtos.csv (salvar_produtos e carregar_produtos)
alterar_produto(produtos) com validações
Persistência em vendas.csv (salvar_vendas e carregar_vendas)
registrar_venda(produtos, vendas)
cancelar_venda(vendas)
Passo 8 — Roteiro de testes finais: checklist de validação de casos válidos, inválidos e persistência ao fechar e reabrir o programa.
        print("Produto não encontrado no catálogo.")
        return
    novo_nome = input(f"Novo nome (Enter para manter '{produto_encontrado[0]}'): ").strip()
    if novo_nome == "":
        novo_nome = produto_encontrado[0]
    preco_texto = input("Novo preço: ").strip().replace(",", ".")
    try:
        novo_preco = float(preco_texto)
    except ValueError:
        print("Erro: o preço precisa ser um número válido.")
        return
    if novo_preco < 0:
        print("Erro: o preço não pode ser negativo.")
        return
    produto_encontrado[0] = novo_nome
    produto_encontrado[1] = novo_preco
    salvar_produtos(produtos)
    print("Produto alterado e salvo com sucesso!")
```
Na função `main()`, ligue a opção `"2"` ao menu:
```python
        if opcao == "1":
            listar_produtos(produtos)
        elif opcao == "2":                              # NOVO
            alterar_produto(produtos)                   # NOVO
        elif opcao == "5":
            classificar_desempenho(vendas)
```
---
## Passo 5 — Persistência de vendas (`vendas.csv`)
Seguindo exatamente o mesmo padrão de `produtos.csv`, vamos salvar e carregar o histórico em `vendas.csv`.
**O que foi modificado/adicionado:**
* Criadas as funções `salvar_vendas(vendas)` e `carregar_vendas(vendas_padrao)`.
* Na função `main()`, substituída a lista fixa pela chamada `vendas = carregar_vendas(vendas_padrao)`.
```python
# NOVO: grava a lista vendas no arquivo vendas.csv
def salvar_vendas(vendas):
    with open("vendas.csv", "w", encoding="utf-8") as arquivo:
        for venda in vendas:
            arquivo.write(f"{venda[0]};{venda[1]};{venda[2]}\n")
# NOVO: lê vendas.csv na abertura ou cria o arquivo inicial
def carregar_vendas(vendas_padrao):
    if not os.path.exists("vendas.csv"):
        salvar_vendas(vendas_padrao)
        return vendas_padrao
    vendas = []
    with open("vendas.csv", "r", encoding="utf-8") as arquivo:
        for linha in arquivo:
            linha = linha.strip()
            if linha:
                partes = linha.split(";")
                produto = partes[0]
