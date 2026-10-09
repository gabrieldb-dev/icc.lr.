# Achados e Perdidos UFRPE: Documento de Requisitos

> Atividade prática de Levantamento de Requisitos (ICC / UFRPE).
> Atividade de prática: não é entregue e não vale nota.

## 1. Equipe
| Nome | Curso |
|------|-------|
| Gabriel Dias Barbosa | Bacharelado em Ciência da Computação |

## 2. Visão geral
**Problema:** objetos perdidos no campus da UFRPE ficam espalhados entre
portarias, secretarias e grupos de mensagem, e raramente voltam ao dono.

**Solução proposta:** a aplicação visa criar um ambiente para que objetos esquecidos possam ser facilmente catalogados e compartilhados para que assim as pessoas que os perderam possam solicitar autoria e então reaver o item outrora perdido.

**Escopo:** centralizar o registro, a consulta e a recuperação de objetos perdidos e encontrados nos diferentes locais da universidade. O sistema será destinado exclusivamente à comunidade acadêmica da UFRPE e permitirá cadastrar objetos, realizar buscas com filtros, registrar perdas, identificar possíveis correspondências, solicitar devoluções e acompanhar a entrega dos itens. Também permitirá que administradores validem os registros e controlem a retirada dos objetos, que ficarão armazenados em pontos de guarda estrategicamente distribuídos pela universidade. A aplicação deverá garantir a segurança dos dados pessoais, a privacidade dos usuários e a acessibilidade em dispositivos móveis e computadores.

## 3. Atores (usuários do sistema)
| Ator | Descrição | O que precisa fazer |
|------|-----------|---------------------|
| Estudante | Aluno com matrícula ativa | Procurar objetos, registrar objetos perdidos e achados |
| Ponto de guarda | Portaria, biblioteca ou secretaria que guarda o objeto | Recebe objeto perdido |
| Administrador | Servidor ou Técnico | Válida a entrada do objeto no sistema e dá baixa na sua entrega |

## 4. Requisitos funcionais
Formato: código, nome, descrição, ator, prioridade e critérios de aceitação.

### RF01: Cadastrar objeto encontrado
- **Descrição:** o sistema deve permitir que um usuário registre um objeto
encontrado, informando categoria, descrição, cor, local, data e foto (opcional).
- **Ator:** Estudante, Ponto de guarda, Administrador
- **Prioridade:** Alta
- **Critérios de aceitação:**
- [ ] Os campos categoria, cor, local e data são obrigatórios.
- [ ] O objeto aparece na busca logo após ser salvo.
- [ ] O sistema informa em qual ponto de guarda o objeto deve ser deixado.

### RF02: Buscar objetos
- **Descrição:** o sistema deve permitir buscar objetos por palavra-chave e
filtrar por categoria, cor, campus/local e período.
- **Ator:** Estudantes
- **Prioridade:** Alta
- **Critérios de aceitação:**
- [ ] Os campos categoria, cor, e data são pré-requisitos para mostrar a lista de objetos.
- [ ] Junto à imagens reais o sistema mostrará imagem equivalentes mas fictícias para comprovar a confiabilidade de quem busca.

### RF03: Registrar objeto perdido
- **Descrição:** o sistema deve permitir que um usuário registre a perda de um objeto, informando categoria, descrição, cor, local, data e foto (opcional).
- **Ator:** Estudantes
- **Prioridade:** Alta
- **Critérios de aceitação:**
- [ ] Os campos categoria, cor, e data são obrigatórios para registro de objeto perdido.
- [ ] O sistema relacionará o objeto ao usuário.

### RF04: Solicitar devolução (reivindicar objeto)
- **Descrição:** o sistema deve apresentar diversas imagens correspondentes a solicitação do usuário e pedir à ele para verificar seu item.
- **Ator:** Estudantes
- **Prioridade:** Alta
- **Critérios de aceitação:**
- [ ] A imagem selecionada pelo usuário deve corresponder ao item cadastrado.
- [ ] O sistema relacionará o objeto ao usuário e o informará o posto para retirada.
- [ ] O sistema retirará o objeto de visualização.

### RF05: Notificar possível correspondência
- **Descrição:** o sistema deverá notificar o usuário ao relacionar uma descrição de item perdido á um novo item catalogado.
- **Ator:** Administrador
- **Prioridade:** Alta
- **Critérios de aceitação:**
- [ ] A descrição do objeto perdido deve ser associada a descrição do objeto achado.
- [ ] O sistema irá verificar a autoria do objeto pelo usúario.

### RF06: Registrar entrega ao dono
- **Descrição:** o administrador deverá registrar a entrega de objeto ao dono, a relacionando com o usuário que verificou sua autoria.
- **Ator:** Administrador
- **Prioridade:** Alta
- **Critérios de aceitação:**
- [ ] O usuário deve apresentar o documento que identifica seu usuário. 

### RF07: Autenticar usuário
- **Descrição:** O sistema deve cadastrar usuário com informações de: nome, email institucional, matricula, CPF, foto (opcional).
- **Ator:** Estudante
- **Prioridade:** Alta
- **Critérios de aceitação:**
- [ ] O usuário deve ser capaz de se cadastrar.
- [ ] O sistema deve autenticar informações de usuário e enviar email de confirmação.


## 5. Requisitos não funcionais
| Código | Categoria | Requisito | Como medir |
|--------|-----------|-----------|------------|
| RNF01 | Responsividade | Funcionar em celular e computador | Testar em telas de 360 px a 1920 px |
| RNF02 | Desempenho | Busca responde rápido | Resultado em até 2 segundos |
| RNF03 | Segurança | Criptografia de dados | Os dados de cadastro não são acessíveis a usuários de tipo estudante |
| RNF04 | Privacidade (LGPD) | Não exibir dados pessoais de terceiros | Documentos oficiais tem informações sensiveis borradas |
| RNF05 | Acessibilidade | Sistema multiplataforma | Testar aplicações web e mobile (IOS / Android) |

## 6. Regras de negócio
- **RN01:** Documentos oficiais (RG, CNH, cartão) não têm foto publicada;
aparecem só como "documento encontrado".
- **RN02:** Objetos não retirados em 30 dias são doados / descartados.
- **RN03:** A retirada exige documento com foto / validação prévia na aplicação.

## 7. Histórias de usuário
- Como **estudante**, quero **buscar meu casaco pela cor e pelo local**,
para **saber se alguém o encontrou sem ir a todas as portarias**.
- Como **vigilante da portaria**, quero **receber o objeto perdido verificando registro feito por que o achou**, para **manter o objeto armazenado adequadamente**.
- Como **administrador**, quero **validar a entrada do ojeto e dar baixa na sua entrega**, para **quem perdeu o objeto possa reave-lo**.

## 8. Dúvidas em aberto
- [ ] Quem pode acessar: só a comunidade UFRPE ou o público em geral? Só a comunidade UFRPE.
- [ ] Os objetos ficam guardados em um só lugar ou em vários pontos? Vários pontos estrátegicamente alocados na universidade.
