# Critérios de Qualificação

Os critérios utilizados para qualificação desta ferramenta foram:

1. Ter requisitos funcionais especificados.
2. Ter sua arquitetura definida.
3. Ter testes que cubram seus requisitos (item 1) em condições normais e de robustez.
4. Ter registrados os resultados dos testes.

Os requisitos foram especificados e podem ser acessados na página [Requisitos](https://github.com/GabrielSSAraujo/dc_cc_analyzer/wiki/Requisitos). A arquitetura foi definida e pode ser acessada na página [Arquitetura](https://github.com/GabrielSSAraujo/dc_cc_analyzer/wiki/Arquitetura). Uma breve discussão sobre os testes é apresentada a seguir.

# Testes

Para o processo de teste, foi adotada a metodologia de testes baseados em requisitos. Essa abordagem permite alinhar o processo de teste às especificações operacionais estabelecidas para a ferramenta. Foram empregadas estratégias distintas para tratar os requisitos funcionais e não funcionais.

No caso do requisito não funcional, foi elaborado um passo-a-passo detalhado contendo as etapas necessárias para a execução da ferramenta em diferentes ambientes operacionais. Essa documentação inclui descrições textuais e representações visuais dos resultados esperados em caso de sucesso, estando devidamente registrados na pasta [tests/users_perspective](https://github.com/GabrielSSAraujo/dc_cc_analyzer/tree/main/tests/users_perspective). Os testes para cobrir o requisito não funcional permitiram a cobertura de alguns requisitos funcionais (REQ-2, REQ-13 e REQ-14).

Já para os demais requisitos, utilizou-se o framework `unittest`, disponibilizado em Python. Este framework foi selecionado por oferecer um conjunto robusto e de fácil utilização para a construção e execução de testes unitários, possibilitando a organização e execução eficiente de suítes de testes. É possível acessar os testes desenvolvidos acessando a pasta [tests](https://github.com/GabrielSSAraujo/dc_cc_analyzer/tree/main/tests) deste repositório.

## Como rodar

A fim de facilitar a execução dos testes desenvolvidos, é possível executar todos de uma vez por meio do comando:

```
python3 tests/run_all_tests.py
```

Para que os testes executem corretamente, garanta que você os execute a partir da pasta raiz do projeto (`cd dc_cc_analyzer`).

## Registro dos resultados
Os registros a respeito das execuções dos testes para os requisitos REQ-1, REQ-2, REQ-13 e REQ-14 podem ser encontrados na pasta [tests/users_perspective](https://github.com/GabrielSSAraujo/dc_cc_analyzer/tree/main/tests/users_perspective), onde os reports gerados e os prints das execuções estão disponibilizados. Para os demais requisitos, foi utilizado a abordagem de testes automáticos, como mencionado anteriormente. A seguir, há um print da execução dos conjuntos de testes presentes na pasta [tests](https://github.com/GabrielSSAraujo/dc_cc_analyzer/tree/main/tests) deste repositório.

![image](https://github.com/user-attachments/assets/2e3383f7-d2ef-4e52-9b60-9bb8d61627b2)