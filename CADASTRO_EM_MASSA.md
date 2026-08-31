# Cadastro em Massa

Cadastra todos os trabalhadores de uma vez: cola a lista inteira, **confere e corrige na
tela**, e só então envia para o sistema. Nada entra na base antes da conferência.

Onde fica: **Menu (☰) → Cadastro em Massa**, ou o atalho **Em massa** no cabeçalho da tela
de Trabalhadores.

## Os três passos

| Passo | O que acontece |
|---|---|
| **1. Colar** | Cola a lista (ou abre um `.csv`/`.txt`). Ninguém foi cadastrado ainda. |
| **2. Conferir** | Cada linha vira um cartão com o status. Dá pra editar, tirar da lista e aplicar valores a todos. |
| **3. Enviar** | Só o que está pronto entra na base. Logo depois aparece o botão **Desfazer**. |

## Formatos que a lista aceita

Um trabalhador por linha. Separadores: **ponto e vírgula**, **vírgula**, **TAB** (colar
direto do Excel) ou **|**.

```
Matrícula;Nome;Função;Área;Encarregado
1052;Carlos Silva;Montador;Pátio 2;Roberto
1053, Ana Souza, Soldador
2001 Maria Alves
José Lima - Ajudante
Maria Santos
```

Reconhecimento automático:

- **Cabeçalho** na primeira linha, incluindo apelidos comuns — `chapa`/`registro` para
  matrícula, `cargo` para função, `setor`/`equipe` para área, `encarregado`/`líder` para
  responsável.
- **Sem cabeçalho**, a ordem é deduzida por linha: número na frente vira matrícula, senão a
  primeira coluna é o nome. Dá para fixar a ordem em *Opções da leitura*.
- **Situação**: `ferias`, `DESLIGADO`, `ativo` — com ou sem acento, maiúscula ou minúscula.
- **Nomes em CAIXA ALTA** viram Nome Próprio (`JOSE DA SILVA` → `Jose da Silva`). Dá pra
  desligar em *Opções da leitura*.
- **Lista numerada** (`1. Fulano`) — o número da numeração é descartado, não vira matrícula.
- **Áreas e funções** casam sem depender de acento ou maiúscula: `Patio 2` encontra
  `Pátio 2` e não cria área repetida.

## Status de cada linha

| Status | Significa | Entra? |
|---|---|---|
| **Novo** | Cadastro novo, sem pendência | Sim |
| **Atualiza** | Matrícula já existe e *Atualizar quem já existe* está ligado | Sim, atualizando |
| **Confira** | Nome repetido na lista ou já existente na base | Sim |
| **Corrigir** | Falta o nome, ou a matrícula repete/já existe | Não |
| **Fora** | Tirado do envio no **×** | Não |

Toque na linha para corrigir qualquer campo antes de enviar.

## Atalhos da conferência

- **Aplicar a todos** — mesma função, área, encarregado ou situação para a lista inteira.
  Com *Só onde estiver vazio* ligado (padrão), preserva o que já veio preenchido.
- **Tirar da lista as N com problema** — manda o resto sem travar no que falta arrumar.
- **Atualizar quem já existe** — mesma matrícula atualiza o cadastro em vez de barrar.
  Aparece sozinho quando o sistema detecta matrículas já cadastradas.
- **Opções da leitura** — ordem das colunas e valores padrão para o que a lista não trouxer.

## Coisas que valem saber

- A conferência é **salva no aparelho**: fechar o app no meio não perde o trabalho.
- **Áreas novas** citadas na lista são criadas no envio; **funções novas** entram na lista
  de funções.
- **Desfazer** apaga só os cadastros criados no último envio, no mesmo dia. Atualizações,
  áreas e funções criadas permanecem.
- Quem entra como **Desligado** fica cadastrado, mas fora do efetivo dos próximos dias.
