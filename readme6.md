Colapso natural de PSO:
Cuando casi todas las partículas ya tienen el mismo mejor personal y el mismo mejor global, la velocidad tiende a cero y el enjambre se compacta.
En tu código no hay mecanismo de diversidad:
En index6.html:542 a index6.html:570 el PSO usa solo atracción a pbest y gbest, sin ruido de exploración ni reinyección de partículas.
Selección global instantánea:
En index6.html:542 a index6.html:555 actualizas gbest cada frame con el mejor actual. Eso hace que todas sigan rápidamente al mismo líder.
Cuando ya convergieron:
Si pbest, gbest y x son casi iguales, en index6.html:561 la ecuación de velocidad queda prácticamente amortiguada por el término inercial 0.6 y el enjambre se vuelve un punto visual.
Entonces, respuesta corta:

Es parcialmente normal en PSO.
En tu simulador está demasiado colapsado porque falta diversidad adaptativa para paisaje dinámico.
