# Seguridad y Riesgos

El ecosistema DeFi es un nuevo ecosistema financiero. Antes de ingresar a DeFi, los usuarios deben comprender los riesgos de inversión y contrato inteligente. Esta sección se centra en los riesgos asociados con BOC.

La siguiente es una lista no exhaustiva de las medidas de seguridad que se implementaron:

1. Para poder evitar pérdidas causadas por vulnerabilidades de código, todos los protocolos deben ser auditados por auditores acreditados.
2. Para reducir el riesgo de un ataque al Oracle, la cotización de la stablecoin debe basarse en ChainLink en lugar del protocolo en sí.
3. Para evitar el riesgo del sistema de cadena causado por tokens anidados y combinaciones de LEGO, el acceso al protocolo de gestión financiera agregada debe tener un registro de operación de seguridad a largo plazo y obtener el permiso de voto de la comunidad.
4. Con el fin de evitar pérdidas transitorias provocadas por las fluctuaciones del mercado, por el momento no se accederá al protocolo de obtención de rendimientos de capital mediante la prestación de servicios de riesgo. Al mismo tiempo, el apalancamiento no se está utilizando para aumentar los rendimientos del capital por el momento.

## Riesgo de dilución de rendimiento

La mayor liquidez de las grandes ballenas puede diluir aún más el rendimiento de los fondos de inversión en un grupo en particular durante los intervalos de reequilibrio.

## Riesgo de contrato inteligente

Los contratos inteligentes debido a las complejidades, incluso auditados por el profesional, aún pueden presentar riesgos y son propensos a ataques y eventos imprevisibles.

## Riesgo de mercado

Los protocolos de préstamo de la contraparte del lado del prestatario también están en riesgo de incumplimiento que no puede ser rectificado por liquidación en un caso extremo de fluctuación del mercado.

## Riesgo de costo de transacción

El reequilibrio automático que se desencadenó por la congestión de la red dará como resultado una tarifa de transacción alta (tarifa de gas) y afectará la tasa de rendimiento final.

## Riesgo de ataque de Oracle

Los oráculos son el puente entre la cadena de bloques y el mundo real. Los oráculos actúan como API en cadena que se pueden consultar para obtener información sobre contratos inteligentes, incluidos, entre otros, información de precios y pronósticos meteorológicos.

El riesgo del oráculo BOC se divide en:

- Si el Oraculo utilizado por la estrategia de protocolo de terceros conectada por BOC es atacada, los beneficios del protocolo ya no serán reales. Esto afectará a que BOC tome decisiones de inversión incorrectas basadas en una cotización incorrecta, lo que a su vez afectará el APY del BOC.

- Si se ataca el Oraculo utilizado por BOC (que actualmente utiliza Chainlink), la valoración de la estrategia dejará de ser precisa, lo que afectará a los depósitos y retiros de los usuarios.