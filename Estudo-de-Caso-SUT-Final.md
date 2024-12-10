# Recursos

O SUT utilizado para a análise neste estudo de caso e o Test Vector estão disponíveis no link a seguir: [sut_final.zip](https://github.com/user-attachments/files/17875193/sut_final.zip).

O relatório de saída produzido pela ferramenta para o SUT está disponível no link a seguir: [report.pdf](https://github.com/user-attachments/files/17877220/report.pdf).

# Análise
## O SUT
A partir do código disponibilizado, foi elaborado um diagrama de blocos, figura a seguir, que detalha as relações entre os componentes internos do sistema. Esse diagrama serve como um recurso visual para mapear as conexões e dependências que existem no código, além de fornecer uma visão clara e organizada das relações.

![block-diagram-sut](https://github.com/user-attachments/assets/0f2f0d88-80cd-4578-8924-01ff082ccba8)

A partir da análise detalhada do diagrama, é possível identificar as relações entre as entradas e as saídas para cada um dos componentes internos do SUT. As entradas que possuem o indicador verde são entradas sem valor atribuído. É possível que essas entradas não possuam influência no resultado da saída desse componente. Já os indicadores em vermelho, demostram saídas que podem ter sido atribuídas dentro dos componentes, mas não é utilizada por um componente posterior durante o fluxo de execução do SUT.

A fim de exemplificar como é feita a analise dos componentes internos, consideremos o componente _f5_. A ferramenta considera que os parâmetros não inicializadas passadas como referência devem ser tratados somente como saídas. Assim, as entradas _o2_ e _f_, não são consideradas como entradas para o componente _f5_. Logo, as entradas serão [_d, b, e_] e as saídas [_o2, b, f_].

Para considerar a cobertura desse componente em relação a entrada _d_, por exemplo, as outras entradas (_b, e_) devem permanecer fixas de um caso de teste para outro, enquanto _d_ varia. Essa variação deve resultar em uma mudança observável em qualquer uma das saídas (_o2, b, f_).

 A tabela a seguir apresenta uma possível forma de mapear a cobertura das relações entre entradas e saídas para o componente _f5_, quando submetidos aos vetores de testes presentes na planilha de Test Vectors.

![image](https://github.com/user-attachments/assets/5613165b-a91e-42d1-a657-03acfa48692a)

Assim, para esse componente do sistema, a cobertura seria de 1 caso coberto em 9 casos totais, resultando em uma cobertura de 11.11%.

A partir da identificação das relações entre entradas e saídas, é possível realizar uma análise para verificar a cobertura total do sistema, considerando o exercício de cada uma das entradas do sistema para cada componente e unindo essas análises para formar a cobertura geral.

## Relatório
Como resultado do processamento do SUT e vetores de teste, a ferramenta gera um relatório contendo 3 seções: resumo da cobertura; relatório de cobertura individual das funções e análise Pass/Fail.

Na seção de resumo da cobertura, pode-se observar algumas informações referentes ao projeto, como localização do código e da suíte de testes analisados, além do percentual de cobertura das analises DC/CC Coverage e de Pass/Fail. Abaixo uma breve apresentação desses resultados.

![report1](https://github.com/user-attachments/assets/7608683a-08fe-483a-95c7-b4a793c8daf7)

* Pass/Fail: 100\% dos testes foram bem-sucedidos, ou seja, a execução do SUT pela ferramenta para cada vetor de teste gerou valores condizentes com as saídas de referência. 
* DC/CC Coverage: Apenas 24.24\% dos acoplamentos foram exercitados. Em outras palavras, nem todos os acoplamentos sofreram variações ao longo da execução dos testes, o que indica pontos de melhoria para ampliar a cobertura. 

Analisando a segunda seção do relatório gerado, é possível discutir em mais detalhes algumas implicações e análises relacionadas aos resultados de cobertura DC/CC, onde é possível observar a relação entre as entradas e saídas de cada função, com destaque em verde para os casos cobertos de cada componente. 

![report2](https://github.com/user-attachments/assets/4a066739-4509-4681-a266-8edb0ee629ec)

Para facilitar a compreensão, é importante considerar as legendas utilizadas:

* NC (Não Coberto): Refere-se as entradas não exercitadas, ou seja, que não conseguiram de forma independente variar e causar uma variação na saída.
* C (x-y): Indica que as entradas foram exercitadas, e em qual caso de teste isso ocorreu (entre os tempos x e y).

A análise da cobertura individual permite identificar claramente quais testes, dentro da suíte de testes, foram capazes de exercitar um determinado conjunto de entrada/saída. Observa-se que os casos de teste principais, que permitiram o exercício de mais combinações de entrada e saída, ocorreram nos intervalos de tempo (0.4s - 0.5s) e (0.2s - 0.3s).

É importante destacar uma característica da ferramenta observada com base nos resultados do DC/CC Coverage. Ela consiste na inviabilidade, em determinados casos, de obter a cobertura total por meio da suíte de testes, pois o critério adotado exige que cada entrada cause uma variação em todas as saídas. Contudo, é possível que algumas entradas não estejam diretamente relacionadas a todas as saídas do componente, o que limita a cobertura máxima atingível. Esse comportamento é inerente à ferramenta, devido ao critério de cobertura escolhido. Para ampliar as análises, podem ser definidos critérios complementares que considerem a cobertura nos casos em que qualquer saída é alterada em resposta a uma determinada entrada.

Outro fato que chama atenção, é a saída _o1_ não variar mesmo quando há uma variação na única entrada do componente, a entrada _c_. Porém, partindo para uma verificação interna do componente _f6_, podemos observar uma característica correspondente a esse comportamento. Note que para _o1_ variar, o valor de _c_, deve ser maior que 120, o que não ocorre nos casos de testes fornecidos como entradas.

![componente-6](https://github.com/user-attachments/assets/e61d2732-2e96-4c4a-bde4-c4d3080a52cb)

Na última seção do relatório, referente à análise Pass/Fail, é possível examinar os valores gerados pela ferramenta em comparação com os resultados esperados. Essa análise permite identificar, em caso de falha, os valores específicos de cada saída, facilitando a compreensão de onde ocorreu o desvio em relação ao comportamento esperado. Além disso, é possível correlacionar a falha com o caso de teste correspondente, permitindo uma investigação detalhada sobre as condições que levaram ao erro.

![report3](https://github.com/user-attachments/assets/aefe7de2-1778-4f81-a67b-ea1154982de9)