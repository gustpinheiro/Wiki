# Visão geral

No total, foram gerados 20 requisitos para a ferramenta, sendo 1 não funcional e 19 funcionais. Dentre os funcionais, 6 são referentes às entradas e ao tratamento das entradas do software, 5 são referentes à sua lógica interna e 8 são referentes às suas saídas, em especial, ao conteúdo do relatório. Os requisitos foram organizados em uma planilha, a qual pode ser acessada pela link a seguir: [requisitos.xlsx](https://github.com/user-attachments/files/17910078/requisitos.xlsx).



O único requisito não funcional diz respeito à portabilidade do software, mais especificamente que "A Ferramenta deve executar em sistemas operacionais Windows e distribuições Linux". Esse requisito foi gerado para aumentar a flexibilidade de uso da ferramenta.

Dentre os requisitos referentes às entradas e seus tratamentos, podemos destacar: REQ-2, REQ-3 e REQ-7. O requisito REQ-2 especifica como a ferramenta deve ser utilizada e quais são suas entradas. O REQ-3 estabelece um dos procedimentos que a ferramenta deve adotar em casos de uso inadequado por parte do usuário. O REQ-7 estabelece a necessidade de verificar se a planilha com os Test Vectors segue o padrão esperado pela ferramenta.

Dentre os requisitos referentes à lógica interna, podemos destacar: REQ-8, REQ-10 e REQ-12. Esses requisitos especificam etapas importantes para o atingimento do objetivo da ferramenta, como a instrumentação do SUT (REQ-8) e a execução do SUT instrumentado (REQ-10), bem como definem o critério que deve ser utilizado para obter a cobertura DC/CC do SUT (REQ-12).

Dentre os requisitos referentes às saídas da ferramenta, podemos destacar: REQ-13, REQ-18 e REQ-19. Esse tipo de requisito foi utilizado para especificar tanto quais deveriam ser as saídas da ferramenta (REQ-13), bem como quais informações deveriam ser apresentadas no relatório, como a porcentagem de cobertura DC/CC medida (REQ-18) e as entradas e saídas de cada função do SUT (REQ-19).
