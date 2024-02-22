# White paper - Project

## Referencias
- Bitcoin
- USDT
- Gensyn (proyecto parecido, tomar contenido y agregar fórmulas y gráficos)
- Solana
- Cartesi
- IPFS


## Aspectos a tener en cuenta
- Debe tener sentido
- Verse complejo pero sin exagerar
- Gráficos, formulas y texto, en ese orden de prioridad
- Staking


## Preguntas
- Que pasa en el caso en que no se concreta el threshold mínimo necesario para determinar cual es la respuesta correcta?
- La idea de determinacion de respuesta por mayoría no se contradice con POS? 


## Ideas
- Caracterizar el escenario en donde un atacante intenta burlar el protocolo de la red como una distribución binomial (Bitcoin, sección 11).
- Un atacante debe conseguir mayoría absoluta de nodos en red. Como el costo mínimo de stacking es 1000usd, si hubiese n nodos honestos, un atacante debería gastar (n+1)*1000 dólares para conseguir mayoría absoluta (más de la mitad de nodos maliciosos). Habiendo tan solo 1000 nodos honestos, el costo por perturbar la red se elevaría a 1.000.000usd.
- Otra cuestión importante en seguridad es evitar que haya nodos vagos, esto es, nodos que replican respuestas de otros nodos para evitar dedicar poder de computo a la hora de calcular las inferencias. Para solucionar este problema se propone realizar auditorías aleatorias cada cierta cantidad t de transacciones.
- Incorporar la siguiente introducción:
￼
- [x] Citar el problema de bloqueo que tuvo Wikipedia en Turquía entre 2017 y 2020 (https://en.wikipedia.org/wiki/Block_of_Wikipedia_in_Turkey) como ejemplo de que es necesaria la falta de censura, tanto desde organismos (como OpenAI) como desde gobiernos, y como el problema pudo ser solucionado alojando Wikipedia en la blockchain de manera descentralizada para evitar bloqueos (https://observer.com/2017/05/turkey-wikipedia-ipfs/)
- [ ] Incorporar cuestiones de seguridad en AI: peligro ante reemplazos de las inferencias o leaks de la data predicha por los modelos. (https://portswigger.net/daily-swig/inference-attacks-how-much-information-can-machine-learning-models-leak)  (https://arxiv.org/pdf/2103.07101.pdf)
- [ ] Completar descripción del caso en el que no hay mayoría.
- [ ] The process of proving your stake produces new blocks and secures the network against malicious attacks. The proof-of-stake protocol also makes Peercoin much less susceptible to a double spend attack. For example, a potential attacker would need to own a majority of the total coin age of all coins participating in the minting process. Given that most coins are in personal wallets and not trading on exchanges, it would require a considerable investment in order to pull off such an attack.  A malicious actor would need to purchase enough coins from the market in order to try mounting an attack against the network. Attempting this vast purchase would cause demand to spike and the price per peercoin to skyrocket. Any attempt to acquire the amount of coins necessary to perform a successful attack would likely bankrupt the attacker in the process.


## Posibles papers y bibliografía para citar
- https://arxiv.org/pdf/2007.05558.pdf | THE COMPUTATIONAL LIMITS OF DEEP LEARNING (citado en Gensyn)
- https://www.peercoin.net/university/#/9-peercoin-proof-of-stake-consensus | PEERCOIN PROOF OF STAKE CONSENSUS
- https://lamport.azurewebsites.net/pubs/byz.pdf | BYZANTINE GENERALS PROBLEM

