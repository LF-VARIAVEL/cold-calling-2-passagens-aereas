### **<span style="color:#2F6BFF">Relatório de Análise Estratégica</span>**: Volatilidade Tarifária e o Preço Atípico de São Francisco no Mercado de Passagens Aéreas

***A) Contexto Analítico e Diagnóstico da Amostra***

O mercado de passagens aéreas é um exemplo clássico de gestão de receitas (*revenue management*): o preço de um mesmo assento varia com a distância, com a intensidade da concorrência na rota e com o perfil do passageiro. A análise descritiva das tarifas de 14 cidades de origem ($n = 14$ para cada destino) para Atlanta e para Salt Lake City permite avaliar o quanto o preço de cada destino é previsível e onde estão os valores que fogem do padrão.

A mensagem central que emerge dos dados é esta (*the big idea*): Salt Lake City tem a média mais alta, mas o que realmente a distingue é a volatilidade, com $CV$ de $34{,}32\%$ contra $20{,}82\%$ em Atlanta. Ainda assim, o único preço fora do padrão está em Atlanta: a tarifa de São Francisco, US\$ 539,60, que ultrapassa a cerca superior em US\$ 62,62.

***B) Tendência Central e Dispersão: Salt Lake City Custa Mais, mas Varia Muito Mais***

**1) Diferença entre as médias (Pergunta 1: US\$ 44,22, ou $12{,}40\%$):** a média de Salt Lake City (US\$ 400,95) supera a de Atlanta (US\$ 356,73). A diferença existe, mas não é expressiva diante da dispersão: ela é menor que o desvio padrão de Atlanta ($s$ = US\$ 74,28) e equivale a cerca de um terço do de Salt Lake City ($s$ = US\$ 137,60). Além disso, é sensível ao outlier: sem São Francisco, a média de Atlanta cai para US\$ 342,66 e a diferença sobe para US\$ 58,29 ($17{,}01\%$). A mediana conta a mesma história com mais clareza (US\$ 420,10 contra US\$ 339,85, uma diferença de US\$ 80,25, ou $23{,}61\%$). Portanto, Salt Lake City tende a ser mais cara, mas, com $n = 14$ e tarifas tão espalhadas, afirmar que a diferença é real exigiria um teste de hipóteses, que já é estatística inferencial.

**2) Preço modal (Pergunta 2: Atlanta em US\$ 359,60 e Salt Lake City amodal):** em Atlanta a moda é US\$ 359,60, que aparece duas vezes (Los Angeles e Phoenix). Em Salt Lake City a distribuição é amodal: as 14 tarifas são diferentes entre si. O pandas devolve os 14 valores como modas justamente porque cada um aparece uma única vez.

**3) Volatilidade ($CV$ de $34{,}32\%$ contra $20{,}82\%$):** em Salt Lake City o $IQR$ é de US\$ 202,00, contra US\$ 65,75 em Atlanta, uma caixa cerca de três vezes mais larga. A leitura dos dados sugere que essa volatilidade é geográfica: as origens do oeste pagam pouco (Las Vegas US\$ 159,60, Denver US\$ 219,60, Phoenix US\$ 267,60, Seattle US\$ 297,60 e Los Angeles US\$ 311,60), enquanto as do leste pagam muito (Filadélfia US\$ 618,40, Cincinnati US\$ 570,10, Miami US\$ 523,20 e Washington US\$ 513,60). O preço acompanha a distância, e por isso a média de US\$ 400,95 descreve mal tanto as origens do oeste quanto as do leste. Em Atlanta, exceto São Francisco, as tarifas ficam agrupadas entre US\$ 249,60 e US\$ 455,60, o que é coerente com um destino que funciona como grande centro de conexões (*hub*), com muitos voos e concorrência entre companhias, fatores que tendem a nivelar os preços.

***C) Posição e Valores Atípicos: O Caso de São Francisco***

**1) Quartis, IQR e cercas (Pergunta 3: um único outlier, US\$ 539,60 em São Francisco):** em Atlanta, $Q_1$ = US\$ 312,60, $Q_3$ = US\$ 378,35 e $IQR$ = US\$ 65,75, o que dá cerca inferior de US\$ 213,98 e cerca superior de US\$ 476,98. A tarifa de São Francisco (US\$ 539,60) é o único valor acima da cerca e, portanto, o único outlier. Em Salt Lake City, $Q_1$ = US\$ 301,10, $Q_3$ = US\$ 503,10 e $IQR$ = US\$ 202,00, com cercas de -US\$ 1,90 e US\$ 806,10. Todas as tarifas, de US\$ 159,60 a US\$ 618,40, ficam dentro delas: não há outlier, apesar da maior dispersão. As duas coisas convivem porque a regra do $IQR$ compara cada preço com o padrão do próprio destino, e em Salt Lake City esse padrão é amplo.

**2) Cobertura de 50% e 75% (Pergunta 4):** o preço que cobre 50% das cidades é a mediana ($Q_2$), e o que cobre 75% é o terceiro quartil ($Q_3$). Para Atlanta são US\$ 339,85 e US\$ 378,35, o que cobre 7 e 10 das 14 cidades. Para Salt Lake City são US\$ 420,10 e US\$ 503,10, o que cobre 7 e 10 das 14. Para o mesmo nível de cobertura de 75%, o orçamento de Salt Lake City precisa ser US\$ 124,75 maior, ou $32{,}97\%$ a mais.

**3) Rota atípica (São Francisco $58{,}78\%$ acima da mediana de Atlanta):** a tarifa deve ser tratada como rota atípica, e não como erro de dado. A distância ajuda a explicar, por ser uma ligação de costa a costa, mas não explica sozinha: Seattle, a uma distância semelhante de Atlanta, paga US\$ 384,60. Isso sugere fatores próprios da rota, como menor concorrência entre as companhias ou forte demanda corporativa saindo de São Francisco. Em precificação, viajantes a negócios têm demanda menos sensível a preço, o que permite às companhias cobrar mais (discriminação de preços). São hipóteses plausíveis que os dados desta amostra não permitem confirmar.

***D) Implicações Práticas para a Tomada de Decisão em Negócios***

**Gestão de viagens corporativas e de compras (quem compra passagens):**

**1) Orçamento por quartis:** em vez da média, adotar como teto de referência o $Q_3$ de cada destino (US\$ 378,35 para Atlanta e US\$ 503,10 para Salt Lake City), que cobre 10 das 14 origens. A média de Salt Lake City (US\$ 400,95) deixa o orçamento curto para as origens do leste e folgado para as do oeste.

**2) Gatilho de investigação:** tratar como alerta qualquer tarifa acima da cerca superior de cada destino (US\$ 476,98 em Atlanta). No caso de São Francisco, buscar rotas alternativas, antecipar a compra ou negociar tarifa corporativa antes de aceitar o preço como normal.

**Gestão de receitas de companhias aéreas e agências (quem vende passagens):**

**1) Salt Lake City:** como o preço acompanha a distância, a política de tarifas deve ser desenhada por faixa de origem (oeste e leste), monitorando os extremos observados (US\$ 159,60 de Las Vegas contra US\$ 618,40 de Filadélfia).

**2) São Francisco para Atlanta:** a tarifa $58{,}78\%$ acima da mediana sinaliza poder de preço. Vale monitorar se ele se sustenta, pois a entrada de um concorrente na rota tende a reduzi-lo.

**Limitação:** com apenas 14 cidades por destino, os resultados descrevem a amostra. Confirmar que as diferenças entre os destinos são reais exige estatística inferencial.
