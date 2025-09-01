# Rota Inteligente: Otimização de Entregas com Algoritmos de IA

## Descrição do Problema
A empresa **Sabor Express**, de delivery de alimentos, enfrenta atrasos e custos altos devido à definição manual das rotas dos entregadores, especialmente em horários de pico. O desafio é desenvolver uma **solução inteligente**, utilizando algoritmos de Inteligência Artificial, capaz de sugerir as **melhores rotas de entrega**, considerando múltiplos pedidos, agrupando entregas próximas e otimizando o trajeto dos entregadores.

## Objetivos
- Reduzir o tempo de entrega e o custo operacional.  
- Agrupar pedidos próximos usando **K-Means**.  
- Encontrar rotas eficientes entre múltiplos pontos utilizando **algoritmos de grafos** (Dijkstra, Nearest Neighbor, 2-opt).  
- Visualizar rotas e clusters de pedidos de forma clara.  

## Abordagem Adotada
1. **Geração de pedidos simulados** com latitude e longitude.  
2. **Agrupamento de pedidos** em clusters usando **K-Means** (número de clusters = número de entregadores).  
3. **Construção de um grafo grade** representando ruas, conectando nós vizinhos com pesos baseados na distância euclidiana.  
4. **Mapeamento de cada pedido** para o nó mais próximo do grafo.  
5. **Cálculo das rotas**:  
   - **All pairs shortest paths** com Dijkstra.  
   - **Nearest Neighbor** para gerar uma rota inicial.  
   - **2-opt** para melhorar a rota heuristicamente.  
6. **Plotagem final das rotas** e clusters no grafo, com destaque para depósito e nós visitados.

## Algoritmos Utilizados
- **K-Means**: para agrupamento de pedidos por proximidade geográfica.  
- **Dijkstra**: para cálculo do caminho mais curto entre nós do grafo.  
- **Nearest Neighbor**: heurística para gerar rotas iniciais.  
- **2-opt**: melhoria de rotas para reduzir distância total percorrida.  

## Diagrama do Grafo
O grafo é uma grade (7x7) mapeada para a latitude e longitude dos pedidos. Cada nó representa um ponto da cidade, conectado a seus vizinhos mais próximos, e o depósito é centralizado.

![Exemplo de grafo com rotas e clusters](exemplo_grafo.png)  
*(Substitua `exemplo_grafo.png` pelo print gerado no código)*

## Análise dos Resultados
- Todas as rotas foram otimizadas dentro de cada cluster de pedidos.  
- A soma das distâncias estimadas para todas as rotas foi reduzida em comparação a um percurso aleatório.  
- Visualmente, as rotas evitam sobreposição excessiva e respeitam o agrupamento geográfico.  
- **Limitações:**  
  - Modelo simulado (pedidos gerados aleatoriamente).  
  - Não considera trânsito ou tempo de espera real.  
  - Heurísticas podem não garantir a distância mínima global.  
- **Sugestões de melhoria:**  
  - Integrar dados reais de trânsito.  
  - Aplicar algoritmos avançados de otimização (ex.: A*, MILP, Reinforcement Learning).  
  - Ajustar dinamicamente o número de clusters conforme a demanda.

## Como Executar o Projeto
1.
Projeto no repositorio
