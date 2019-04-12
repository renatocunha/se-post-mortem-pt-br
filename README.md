# Software Engineer 101 - Post-Mortem

--------------

![alt](src/post-mortem.png)
<br>

**O que é Post-Mortem**
<br>
 Post-Mortem é uma ferramenta pela qual os desenvolvedores podem aprender com as dificuldades enfrentadas no passado, compartilhar conheciment e sobretudo, estratégias são criadas para futuro. 

Estas reuniões geralmente são feitas após um periodo de crise, ou ao final de um projeto, com o intuito de criar a cultura de analizar de maneira imparcial os fatos e melhorar os processos de desenvolvimento.

Embora parecidas com as *sprint-reviews* as reuniões de Post-Mortem devem ter um foco mais tecnico e objetivo. 

Durante uma reunião Post-Mortem apenas uma coisa deverá ser discutida, o tema em pauta deve ser o mais refinado possível.

**Reuniões Post-Mortem** 

<br>
*Extraido do Livro Manual Devops*

- Reunião é dirigida por um "Facilitador", esta pessoa deve conduzir o encontro e garantir que as pessoas mantenham o foco no processo, deve evitar que culpados sejam apontados. O pricipal papel do Facilitador é evitar que 'culpados' sejam apontados.

- Durante uma reunião de post-mortem os participantes devem traçar uma linha do tempo do incidente e incluir quando, quem e como foi detectado o incidente, qual etapa do processo ele foi descoberto ( automação, teste manual ou cliente) e em que momento o incidente foi corrigido.
 
- A Equipe pode montar um pequeno documento para ajudar na composição da linha do tempo respondendo perguntas como o exemplo a seguir:
    -> Impacto ? - Qual o impacto total do evento - como isso afetou nossos clientes)
    -> Houve Paralização ? - O problema possuía saída de contorno? Quanto tempo custou ao cliente?
    -> Quando detectamos? - Quando e quanto tempo levamos para detectar o problema;
    -> Quando resolvemos? - Quando e quanto tempo levamos para corrigir o problema? 

- A Equipe cria uma lista de fatores que contribuiram para o incidente, humanos e tecnicos, e fatores que poderiam coebir o incidente. O time pode realizar um **brainstorm** e criar rotulos para estes fatores ex.:
    - Pressa
    - Débito técnico
    - Tecnologia
    - Automação
    Nenhuma sugestão deve ser descartada.

- Ao final da reunião, com base na linha do tempo e a lista de fatores os Dev's criam um pequeno relatório, para documentar, e casp ncessário explicar como lidar com crises parecidas (*manual do desespero*) e sobretudo como evitar que elas ocorram (*Lean*).  

- Além do manual de como lidar com a crise, caso sejam listados processos que podem ser alterados/criados, um dos participantes é elegido como responsável, e recebe um prazo para que estas ações sejam implementadas.

##Relatório de falhas
 
Os relatórios de falhas/bugs são ferramentas para documentar ocorrências e balizar ações preditivas, além de poupar tempo de outros Dev's, para os momentos em que ele tenha de lidar com casos similares. 

**Exemplos de Reports**

*Processo*

```
**Ocorrência 01-Jan19**
Ferramenta de Status estava indisponível e posteriormente o certificado era apresentado como inválido.

**Problema identificado**
O serviço Docker não estava iniciado. Certificados não estavam atualizados.

**Medidas tomadas para solução**
iniciamos o serviço com "systemctl restart docker".
tentamos alterar a tarefa de cópia dos certificados porem apresentava problemas,
copiamos manualmente e a situação foi normalizada.
```

*Bug*

```
**Ocorrência 03-Dez18**
Error log ao acessar a rotina de pagamentos.

**Problema identificado**
Query da função de pagamentos exeucta instrução SQL que não funciona em bancos Oracle.

**Medidas tomadas para solução**
- Criado tratamento de verificação do tipo de SGBD antes da montagem da query;
- Revisada todas as chamadas de query que utilizem a instrução supracitada;
- Novas funcionalidades devem possuir requisito funcional de atender todos os SGBD's homologados.
```

*referências*



[Manual de DevOps](https://www.amazon.com.br/Agilidade-Confiabilidade-Seguran%C3%A7a-Organiza%C3%A7%C3%B5es-Tecnol%C3%B3gicas/dp/8550802697)

[zapty](https://zapty.com/blog/post-mortem-meeting-template/)

[temagantt](https://www.teamgantt.com/blog/post-mortem-meeting-template-and-tips)