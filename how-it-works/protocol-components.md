# Componentes del protocolo

## Blockchains incorporados

BOC seleccionó [blockchain](../more/appendix.md#blockchain-network) son compatibles con [Ethereum Virtual Machine (EVM)](../more/appendix.md#ethereum-virtual-machine-evm), en realidad BOC está conectado con Ethereum, BNB Chain y Polygon chain.

### Ethereum

**Ethereum** es una plataforma blockchain descentralizada de código abierto con funciones de [contrato inteligente](../more/appendix.md#smart-contract), cuya [criptomoneda](../more/appendix.md#criptomoneda) nativa es ETH. En diciembre de 2021, Ethereum se convirtió en la segunda criptomoneda más valiosa por capitalización de mercado después de Bitcoin, y en la blockchain más utilizada.

El concepto de Ethereum fue propuesto por primera vez entre 2013 y 2014 por el programador Vitalik Buterin tras inspirarse en Bitcoin como "la próxima generación de criptodivisas y plataforma de aplicaciones descentralizadas". El desarrollo de Ethereum comenzó a través del crowdfunding ICO en 2014.

Ethereum también se conoce como la "plataforma blockchain de segunda generación", solo superada por Bitcoin.

### BNB

**Binance Smart Chain** (antes llamada BSC) es una blockchain compatible con la máquina virtual Ethereum en paralelo a la cadena Binance. Es un proyecto de vanguardia en la industria de los criptoactivos. Al introducir el mecanismo de consenso Proof of Stake Authority (PoSA), BNB crea un ecosistema de validación que permite a los nodos, a los titulares de tokens, a los desarrolladores y a los usuarios disfrutar de todos los beneficios de la blockchain, como un mayor rendimiento y un abundante espacio de innovación.

El 15 de febrero de 2022, la bolsa de criptomonedas Binance anunció que la cadena inteligente original de Binance (BSC) pasará a llamarse cadena BNB. BNB es la criptodivisa de la plataforma de intercambio Binance que impulsa el ecosistema BNB Chain, y es uno de los tokens de utilidad más populares del mundo.

### Polygon

**Polygon** es un protocolo para construir e interconectar redes de blockchain compatibles con Ethereum. El proyecto se lanzó en la India en 2017 con el nombre original de Matic Network. En febrero de 2021, el nombre del proyecto se cambió a Polygon. La criptodivisa del proyecto Polygon es MATIC, una de las 20 principales criptodivisas por capitalización de mercado negociada en los principales intercambios.

## Incorporación de Stablecoins

Con el fin de evitar el miedo psicológico causado por las fluctuaciones del valor de la moneda digital y las pérdidas de los fondos de creación de mercado, el protocolo BOC ha seleccionado sólo [activos de moneda estable](../more/appendix.md#stablecoin), y solo se limita a aquellos con plena [garantía](../more/appendix.md#colateral) proporcionada por moneda legal o por stablecoins.

Las stablecoins deben cumplir las siguientes condiciones

* Pasar la auditoría
* Disponer de un seguro
* Las cotizaciones de las stablecoins deben basarse en ChainLink y no en el propio protocolo para reducir los ataques de oráculo.
* Escala superior a 1.000 millones de dólares

Las stablecoins estratégicas actualmente seleccionadas son: DAI, USDC, USDT, BUSD, USDP, TUSD, LUSD.

### DAI

[**DAI**](https://makerdao.com/en/) es una criptodivisa stablecoin diseñada para mantener su valor lo más cerca posible del dólar a través de un sistema automatizado de contratos inteligentes en la blockchain de Ethereum.

[https://makerdao.com/en/](https://makerdao.com/en/)

### USDC

[**USD Coin**](https://www.centre.io/usdc) (USDC) es una stablecoin digital vinculada al dólar estadounidense que opera en las blockchains de Ethereum, Stellar, Algorand, Hedera Hashgraph y Solana. En enero de 2022, el USDC en circulación es de 45.200 millones de dólares.

[https://www.centre.io/usdc](https://www.centre.io/usdc)

### USDT

[**USDT**](https://tether.to/en/), también conocida como USDT, es una controvertida criptodivisa emitida por Tether Limited, que está controlada por los propietarios de Bitfinex. USDT es una moneda estable. Lanzada en 2014, la moneda es una plataforma basada en blockchain que facilita digitalmente el uso de monedas fiduciarias.

[https://tether.to/en/](https://tether.to/en/)

### BUSD

[**Binance USD**](https://www.binance.com/en/busd) (BUSD) es una nueva stablecoin lanzada por Binance y Paxos, que está vinculada 1:1 al dólar estadounidense.

[https://www.binance.com/en/busd](https://www.binance.com/en/busd)

### USDP

[**Pax Dollar**](https://paxos.com/usdp/) (USDP) es una stablecoin con garantía fiduciaria que está vinculada 1:1 al dólar estadounidense.

[https://paxos.com/usdp/](https://paxos.com/usdp/)

### TUSD

[**TrueUSD**](https://www.trusttoken.com) (TUSD) es una stablecoin vinculada al USD emitida por Trusttoken.

[https://www.trusttoken.com/](https://www.trusttoken.com/)

### LUSD

[**LUSD**](https://www.liquity.org/) es una stablecoin con paridad en USD emitida por liquidity Protocol.

[https://www.liquity.org/](https://www.liquity.org/)

## Selección de estrategia de protocolo

Después de seleccionar la moneda estable, sus estrategias correspondientes deben cumplir las siguientes condiciones:

* No tener comisión por depósito o retiro.
* No tener un período de bloqueo, por lo que los fondos se pueden retirar rápidamente.
* Sin limitación en la cantidad de fondos para un inversor.
* Todos los protocolos deben ser auditados para evitar pérdidas potenciales causadas por vulnerabilidades de código.
* El protocolo de gestión financiera agregada debe contar con un registro de operación de seguridad a largo plazo, también obtiene el permiso de las comunidades mediante votación. Por lo tanto, los riesgos del sistema en cascada causados ​​por fichas anidadas y combinaciones de LEGO pueden evitarse.
* No utilizar protocolos de magnificación de rendimientos de capital mediante la prestación de servicios de riesgo o apalancamiento, evitando así las pérdidas provocadas por las fluctuaciones del mercado.
* El DEX al que se accedió por primera vez y el protocolo de préstamo deben ser los protocolos de primera línea preferidos en cada cadena de bloques y también contar con buenos registros de operaciones de seguridad.
* El protocolo debe asignar la cadena de capital de forma inteligente, que obedece siempre a dos reglas: maximizar los rendimientos y descentralizar los riesgos del capital.

Los protocolos actualmente seleccionados son

* Ethereum: Convex, DODO, SushiSwap, Balancer, etc.
* Cadena BNB: DForce, Synapse, Venus, DODO, Belt, Pancakeswap, Alpaca, etc.
* Polygon: DODO, Synapse, Quickswap, Balancer, Aave, Curve, SushiSwap, etc.

### Aave

[**Aave**](https://app.aave.com/) es un protocolo de préstamo descentralizado de código abierto que proporciona a los usuarios servicios de depósito y préstamo. Los tipos de interés de los depósitos y préstamos de los usuarios, tanto del prestatario como del prestamista, se calculan mediante algoritmos basados en el volumen de préstamos y el volumen de depósitos de la plataforma, y ésta utiliza el oráculo de Chainlink para garantizar la equidad del precio de la garantía. Según los datos de [DeFi Pulse](https://www.defipulse.com/), a 30 de marzo de 2022, el volumen total de bloqueo de fondos de Aave era de aproximadamente 11.790 millones de dólares, ocupando el segundo lugar en el volumen de bloqueo de aplicaciones de DeFi.

### Curva

[**Curve**](https://curve.fi/) es un intercambio descentralizado desplegado en Ethereum. Curve está diseñado para el comercio entre stablecoins con bajas comisiones y deslizamientos a través de un protocolo de creador de mercado automatizado. Es un agregador de liquidez descentralizado, y cualquiera puede añadir sus propios activos al pool de liquidez para obtener beneficios de creación de mercado. Según los datos de [DeFi Pulse](https://www.defipulse.com/), al 30 de marzo de 2022, el volumen total de bloqueo de fondos de Curve era de aproximadamente 10.790 millones de dólares, ocupando el tercer lugar en el volumen de bloqueo de aplicaciones de DeFi.

### Convex

[**Convex**](https://www.convexfinance.com/) es una plataforma única para la estaca de CRV y la minería de liquidez en Ethereum que se dedica a simplificar el uso de Curve.

Como agregador de ingresos en la cadena Ethereum, Convex pretende utilizar el token CVX para simplificar el proceso de bloqueo y estaqueo de Curve y CRV a través de una interfaz sencilla y fácil de usar, y mejorar la compensación de los titulares de tokens CRV y los proveedores de liquidez. Esto facilita el desarrollo del ecosistema CRV. Según los datos de [DeFi Pulse](https://www.defipulse.com/), al 30 de marzo de 2022, el total de fondos bloqueados de Convex ascendía a unos 10.100 millones de dólares, ocupando el cuarto lugar en las aplicaciones de DeFi.

### Uniswap

[**Uniswap**](https://uniswap.org/) es un intercambio descentralizado desplegado en Ethereum. El protocolo Uniswap facilita las transacciones automatizadas entre tokens de criptodivisas en la blockchain de Ethereum mediante el uso de contratos inteligentes. A partir de octubre de 2020, se estima que Uniswap es el mayor intercambio descentralizado y el cuarto mayor intercambio de criptodivisas por volumen de negociación diario. Según los datos de [DeFi Pulse](https://www.defipulse.com/), al 30 de marzo de 2022, el total de fondos bloqueados de Uniswap ascendía a unos 7.040 millones de dólares, ocupando el sexto lugar en aplicaciones DeFi.

### Balancer

[**Balancer**](https://balancer.fi/) es un intercambio descentralizado desplegado en Ethereum. Balancer utiliza creadores de mercado automáticos para lograr la función de transacciones descentralizadas. Los usuarios de las transacciones pueden elegir los pares de operaciones para negociar y pagar las tasas de transacción, mientras que los proveedores de liquidez pueden obtener una parte de las tasas. Según los datos de [DeFi Pulse](https://www.defipulse.com/), al 30 de marzo de 2022, el volumen total de bloqueo de fondos de Balancer era de unos 2.190 millones de dólares estadounidenses, ocupando el sexto lugar en el volumen de bloqueo de aplicaciones DeFi.

### SushiSwap

[**SushiSwap**](https://app.sushi.com/swap) fue originalmente una bifurcación de Uniswap, construida sobre el código de Uniswap, aunque introduciendo algunas diferencias clave. Una de las mayores diferencias es que las recompensas se emiten en tokens SUSHI. Los proveedores de liquidez de SushiSwap son recompensados con el token nativo del protocolo, SUSHI, que también es un token de gobernanza. A diferencia de Uniswap (UNI), los titulares de SUSHI pueden seguir obteniendo rendimientos incluso después de dejar de proporcionar liquidez. Según [DeFi Pulse](https://www.defipulse.com/), al 30 de marzo de 2022, entre las clasificaciones de los intercambios centralizados, el volumen total de bloqueo de fondos de Sushiswap era de aproximadamente 1.680 millones de dólares, ocupando el 11º lugar en el volumen de bloqueo de aplicaciones DeFi.

### Quickswap

[**Quickswap**](https://quickswap.exchange/#/) es un intercambio descentralizado de capa 2, similar a Uniswap y Sushiswap, que utiliza el método AMM. Cualquiera puede invertir dinero en Quickswap, proporcionar liquidez y obtener ingresos apostando de nuevo tokens de liquidez. El token de Quickswap, QUICK, se utiliza como token de gobernanza, y sus titulares pueden presentar propuestas de cambios en el protocolo. Según los datos de [DeFi Pulse](https://www.defipulse.com/), al 30 de marzo de 2022, entre los rankings de intercambios centralizados, los fondos totales bloqueados de Quickswap ascendían a unos 473 millones de dólares, ocupando el puesto 22 entre las aplicaciones DeFi.

### DODO

[**DODO**](https://app.dodoex.io/) es una plataforma de negociación descentralizada que utiliza un algoritmo original de Creador de Mercado Proactivo (PMM) para proporcionar una liquidez eficiente en la cadena para los activos de Web3, permitiendo a todo el mundo emitir y negociar fácilmente los activos de Web3. DODO no sólo proporciona liquidez por sí mismo, sino que también agrega la liquidez de otras bolsas. Esto permite a DODO ofrecer los mejores precios de toda la red. Según los datos de [DeFi Pulse](https://www.defipulse.com/), al 30 de marzo de 2022, el volumen total de bloqueo de fondos de DODO era de aproximadamente 47.700 millones de dólares, ocupando el puesto 52 en el volumen de bloqueo de aplicaciones DeFi.

### dForce

[**dForce**](https://dforce.network/) está comprometida con la construcción de una matriz integrada e interoperable de protocolos financieros abiertos y protocolos de divisas, incluyendo protocolos de préstamo (grupos de liquidez global, mercados que generan intereses), protocolos basados en activos (stablecoins multidivisa, activos sintéticos, etc.), agregadores de liquidez, creadores de mercado automáticos, etc. Al 30 de marzo de 2022, el volumen total de fondos bloqueados de dForce era de aproximadamente 15.400 dólares, y las aplicaciones de DeFi ocupaban el puesto 69 en volumen de bloqueo.

### Synapse

[**Synapse**](https://synapseprotocol.com/landing) fue actualizado y renombrado a partir de Nerve Finance, un protocolo de liquidez anónimo de cadena cruzada en la cadena BNB original.

Synapse adopta un esquema de validación de computación multipartidista (MPC) entre cadenas y un esquema de firma de umbral para soportar activos, llamadas de contratos inteligentes, etc. Synapse conecta diferentes blockchains para una interoperabilidad fácil y segura; los desarrolladores también pueden construir aplicaciones reales de cadena cruzada, incluyendo DEXs de cadena cruzada, plataformas de préstamos, sistemas de márgenes, mercados de derivados, agregadores de ingresos, y más.

### Venus

[**Venus**](https://app.venus.io/dashboard) es un sistema de mercado de divisas descentralizado impulsado por stablecoin sintético en la cadena BNB, que proporciona a los usuarios soluciones de préstamo de criptodivisas sin necesidad de custodia de fondos por parte de terceros o de entidades centralizadas que ejerzan más control sobre el protocolo.

Los prestatarios en Venus pueden obtener préstamos instantáneos en stablecoins después de mantener la criptodivisa. Esto permite a los usuarios obtener fondos adicionales sin tener que vender sus activos digitales que no sean stablecoins. Por otro lado, los prestamistas pueden depositar stablecoins (y otras criptodivisas diferentes) en la plataforma para obtener ingresos pasivos. Lo que hace único a Venus es la forma en que promueve su propia stablecoin sintética dentro del ecosistema de criptodivisas. Las stablecoins sintéticas pueden mantener un valor estable a largo plazo sin tener los activos del mundo real a los que están vinculadas (por ejemplo, a través de algoritmos, esquemas de incentivos del ecosistema o utilizando otras formas de garantía).

### Pancakeswap

[**Pancakeswap**](https://pancakeswap.finance/) es un intercambio descentralizado en BNB Chain. Los usuarios pueden obtener ingresos de creación de mercado proporcionando liquidez a la plataforma, y ganar tokens de Cake apostando.

### Alpaca

[**Alpaca**](https://app.alpacafinance.org/lend) es el mayor protocolo de préstamos en la cadena BNB que proporciona granjas apalancadas. Alpaca ayuda a los prestamistas a obtener ingresos y proporciona a los prestatarios préstamos apalancados para la posición de la granja con insuficiente garantía, lo que maximiza el beneficio principal de la minería de los agricultores y puede generar múltiples rendimientos.

## Oráculos incorporados

Los oráculos son fuentes de datos que conectan a Ethereum con información del mundo real fuera de la cadena para que el usuario pueda consultar los datos en los contratos inteligentes. Permite que ciertos contratos inteligentes respondan al mundo externo incierto, y es la única manera de que los contratos inteligentes interactúen con el mundo exterior, y también es la interfaz entre blockchain y el mundo real.

### Chainlink

[**Chainlink**](https://chain.link/) es una red de oráculos descentralizada que sirve de puente entre los contratos inteligentes (como los de Ethereum) y sus datos externos. La propia blockchain no puede conectarse a aplicaciones externas de forma fiable. Chainlink no es una única red de oráculos, sino un ecosistema de muchas redes de oráculos descentralizadas que funcionan en paralelo, cuyo token es LINK.

## Dirección del contrato de protocolo.

### Ethereum

| Contrato BOC                                                                                            | Contrato del protocolo de la tercera parte                                                                                                                                                              |
| ------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Vault](https://etherscan.io/address/0xd5C7A01E49ab534e31ABcf63bA5a394fF1E5EfAC)                        |                                                                                                                                                                                                         |
| [Balancer3CrvStrategy](https://etherscan.io/address/0xa4bc7002d89ef7966c5b2fd70963eaa7a632bb19)         | [Balancer Vault](https://etherscan.io/address/0xBA12222222228d8Ba445958a75a0704d566BF2C8)                                                                                                               |
| [DodoUsdtUsdcStrategy](https://etherscan.io/address/0x88b7068a365a92fe648c6d6a99cc58a583756df5)         | [DSP](https://etherscan.io/address/0xC9f93163c99695c6526b799EbcA2207Fdf7D61aD) [DODOMine](https://etherscan.io/address/0xaeD7384F03844Af886b830862FF0a7AFce0a632C)                                      |
| [DodoDaiUsdtStrategy](https://etherscan.io/address/0xcace5387e7154594e0e95aa82f7779b2a0d8c9dc)          | [DSP](https://etherscan.io/address/0x3058EF90929cb8180174D74C507176ccA6835D73) [DODOMine](https://etherscan.io/address/0x1A4F8705E1C0428D020e1558A371b7E6134455A2)                                      |
| [SushiKashiUsdcLinkStrategy](https://etherscan.io/address/0x839672fff7bf86a273c9c1eb4ee72ca2496c7142)   | [KashiPairMediumRiskV1](https://etherscan.io/address/0x4f68e70e3a5308d759961643AfcadfC6f74B30f4)                                                                                                        |
| [SushiKashiUsdtXsushiStrategy](https://etherscan.io/address/0xae4556510a43ff37df27d16a7ae8a08440a132da) | [KashiPairMediumRiskV1](https://etherscan.io/address/0xC84Fb1F76cbdd3b3491E81FE3ff811248d0407e9)                                                                                                        |
| [SushiKashiUsdtWethStrategy](https://etherscan.io/address/0x0adbfc6db10efd02786e3f590127079e74e4c128)   | [KashiPairMediumRiskV1](https://etherscan.io/address/0xfF7D29c7277D8A8850c473f0b71d7e5c4Af45A50)                                                                                                        |
| [SushiKashiUsdcWethStrategy](https://etherscan.io/address/0xfc3dd2cabf81999eb9e48ffb248ab048fccf348d)   | [KashiPairMediumRiskV1](https://etherscan.io/address/0xB7b45754167d65347C93F3B28797887b4b6cd2F3)                                                                                                        |
| [SushiKashiUsdcXsushiStrategy](https://etherscan.io/address/0x58c505ca34d908d7cb8349aaf6df7b942fe31a2e) | [KashiPairMediumRiskV1](https://etherscan.io/address/0x6EAFe077df3AD19Ade1CE1abDf8bdf2133704f89)                                                                                                        |
| [ConvexIronBankKrwStrategy](https://etherscan.io/address/0xb7e3eb6bbdd0cb9206ebd7c4d8351b52f61ca42b)    | [Iron Ban iKrw](https://etherscan.io/address/0x3c9f5385c288cE438Ed55620938A4B967c080101), [Curve.fi Factory Plain Pool ibKRW](https://etherscan.io/address/0x8461A004b50d321CB22B7d034969cE6803911899)  |
| [ConvexIronBankJpyStrategy](https://etherscan.io/address/0x0e0963f34560bc337513319c4a7bf65f4c083907)    | [Iron Ban iJPY](https://etherscan.io/address/0x215F34af6557A6598DbdA9aa11cc556F5AE264B1), [Curve.fi Factory Plain Pool ibJPY](https://etherscan.io/address/0x8818a9bb44Fbf33502bE7c15c500d0C783B73067)  |
| [ConvexIronBankGbpStrategy](https://etherscan.io/address/0x562c03b7822c9bcb9d19749a328d468eb8a15f48)    | [Iron Ban iGBP](https://etherscan.io/address/0xecaB2C76f1A8359A06fAB5fA0CEea51280A97eCF), [Curve.fi Factory Plain Pool ibGBP](https://etherscan.io/address/0xD6Ac1CB9019137a896343Da59dDE6d097F710538)  |
| [ConvexIronBankEurStrategy](https://etherscan.io/address/0x809491dc62e9177733e0ce11b0f73cd873d47ed3)    | [Iron Ban iEUR](https://etherscan.io/address/0x00e5c0774A5F065c285068170b20393925C84BF3), [Curve.fi Factory Plain Pool ibEUR](https://etherscan.io/address/0x19b080FE1ffA0553469D20Ca36219F17Fcf03859)  |
| [ConvexIronBankChfStrategy](https://etherscan.io/address/0x560419b9183db2c9fb8ae32dbc93bef5b34c7826)    | [Iron Ban iCHF](https://etherscan.io/address/0x1b3E95E8ECF7A7caB6c4De1b344F94865aBD12d5), [Curve.fi Factory Plain Pool ibCHF](https://etherscan.io/address/0x9c2C8910F113181783c249d8F6Aa41b51Cde0f0c)  |
| [ConvexIronBankAudStrategy](https://etherscan.io/address/0xca41275733bba2831487206631cb46ad40bfda5d)    | [Iron Ban iUSDT](https://etherscan.io/address/0x48759F220ED983dB51fA7A8C0D2AAb8f3ce4166a), [Curve.fi Factory Plain Pool ibAUD](https://etherscan.io/address/0x3F1B0278A9ee595635B61817630cC19DE792f506) |
| [Convex3CrvStrategy](https://etherscan.io/address/0x4d4700c777be1e11ec3af9465c90280788329964)           | [Curve.fi DAI/USDC/USDT Pool](https://etherscan.io/address/0xbEbc44782C7dB0a1A60Cb6fe97d0b483032FF1C7)                                                                                                  |
| [ConvexBusdStrategy](https://etherscan.io/address/0x264644dfbab5df335a05532a730421491808a7e5)           | [Curve.fi BUSD Swap](https://etherscan.io/address/0x79a8C46DeA5aDa233ABaFFD40F3A0A2B1e5A4F27)                                                                                                           |
| [ConvexLusdStrategy](https://etherscan.io/address/0x1f20dfb2b2ddbef30ea7c404d31970614dc5d6b5)           | [LUSD3CRV-f](https://etherscan.io/address/0xEd279fDD11cA84bEef15AF5D39BB4d4bEE23F0cA)                                                                                                                   |
| [ConvexBusdV2Strategy](https://etherscan.io/address/0x12896914a7fe92236d167c0c498b490d3aefd3e2)         | [Curve.fi BUSD V2](https://etherscan.io/address/0x4807862AA8b2bF68830e4C8dc86D0e9A998e085a)                                                                                                             |
| [ConvexYStrategy](https://etherscan.io/address/0x22ffc3b6b250c8bedee7e67c8e3ca6e2aaac63a4)              | [Curve.fi y Swap](https://etherscan.io/address/0x45F783CCE6B7FF23B2ab2D70e416cdb7D6055f51)                                                                                                              |
| [ConvexUsdtStrategy](https://etherscan.io/address/0x23a25fa21584b4b8f1348ac74396bf0ee8a72b6f)           | [Curve.fi USDT Swap](https://etherscan.io/address/0x52EA46506B9CC5Ef470C5bf89f17Dc28bB35D85C)                                                                                                           |
| [ConvexTusdStrategy](https://etherscan.io/address/0x968ebccd0e77644242ffb4468abe93774f75f34f)           | [TUSD3CRV-f](https://etherscan.io/address/0xEcd5e75AFb02eFa118AF914515D6521aaBd189F1)                                                                                                                   |
| [ConvexPaxStrategy](https://etherscan.io/address/0xf08fda0293cc8706ae1e280a9dc194c137cb63be)            | [pax-usdp3](https://etherscan.io/address/0xc270b3B858c335B6BA5D5b10e2Da8a09976005ad)                                                                                                                    |
| [ConvexCompoundStrategy](https://etherscan.io/address/0x02733188d0cbc87b4046b5ad12b9f3c8f3879c14)       | [Curve.fi Compound Swap](https://etherscan.io/address/0xA2B47E3D5c44877cca798226B7B8118F9BFb7A56)                                                                                                       |
| [ConvexAaveStrategy](https://etherscan.io/address/0x7f3bd67d7366dbc6b149f606cfa9c8fcdb72d9e2)           | [Curve.fi aDAI/aUSDC/aUSDT Pool](https://etherscan.io/address/0xDeBF20617708857ebe4F679508E7b7863a8A8EeE)                                                                                               |
| [YearnEarnTusdStrategy](https://etherscan.io/address/0x5c09ab7a2e09cc0f1d2e7f7ed189a7477c8e9623)        | [yearn yTUSD Token](https://etherscan.io/address/0x73a052500105205d34Daf004eAb301916DA8190f)                                                                                                            |
| [GUniUsdcDai100Strategy](https://etherscan.io/address/0x6488b7756e4338d73b85c61a67ca33921be59c88)       | [Gelato Uniswap DAI/USDC LP](https://etherscan.io/address/0x50379f632ca68D36E50cfBC8F78fe16bd1499d1e)                                                                                                   |

### BNB Chain

| Contrato BOC                                                                                      | Contrato del protocolo de la tercera parte                                                                                                                                                                  |
| ------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Vault](https://bscscan.com/address/0x76609c83dD684F0D4c0F0c9849db0a1b5a96CAB2)                   |                                                                                                                                                                                                             |
| [PancakeDaiBusdStrategy](https://bscscan.com/address/0x3fa2b30bfa5816b115b648d42955d3c3cb7bc368)  | [PancakeSwap Router v2](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E) [PancakeSwap Main Staking Contract](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E) |
| [PancakeTusdBusdStrategy](https://bscscan.com/address/0x3c87c8a62bc56b9663a256999c5aa333ce459857) | [PancakeSwap Router v2](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E) [PancakeSwap Main Staking Contract](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E) |
| [PancakeUsdcBusdStrategy](https://bscscan.com/address/0x05898f26ebfb39de28c55a7dc3d2ff062aa8defa) | [PancakeSwap Router v2](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E) [PancakeSwap Main Staking Contract](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E) |
| [PancakeUsdcUsdtStrategy](https://bscscan.com/address/0x06695568007119a0f79720cb0ad481c9ce640e9c) | [PancakeSwap Router v2](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E) [PancakeSwap Main Staking Contract](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E) |
| [PancakeUsdtBusdStrategy](https://bscscan.com/address/0xeccc75f9e1ba708c25202c744ea61dc93dc9a2f0) | [PancakeSwap Router v2](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E) [PancakeSwap Main Staking Contract](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E) |
| [AlpacaTusdStrategy](https://bscscan.com/address/0x7983b99faf9854d82bbd100302defff4f6fd9b51)      | [ibTUSD](https://bscscan.com/address/0x3282d2a151ca00BfE7ed17Aa16E42880248CD3Cd)                                                                                                                            |
| [AlpacaUsdtStrategy](https://bscscan.com/address/0x568dced4cb4114359854f052fc5b776f6c6d12dc)      | [ibUSDT](https://bscscan.com/address/0x158Da805682BdC8ee32d52833aD41E74bb951E59)                                                                                                                            |
| [AlpacaBusdStrategy](https://bscscan.com/address/0x8178f4a3c7acc168cba50c8a70b4de8b63d6d892)      | [ibBUSD](https://bscscan.com/address/0x7C9e73d4C71dae564d41F78d56439bB4ba87592f)                                                                                                                            |
| [VenusTusdStrategy](https://bscscan.com/address/0x175724af9ec5e3e7b71934d31b5db4f8c4146db4)       | [vTUSD](https://bscscan.com/address/0x08CEB3F4a7ed3500cA0982bcd0FC7816688084c3)                                                                                                                             |
| [VenusUsdtStrategy](https://bscscan.com/address/0x21b31dc834588f81d2ae3fe64f3ce3c5bdbd070d)       | [VUSDT](https://bscscan.com/address/0xfD5840Cd36d94D7229439859C0112a4185BC0255)                                                                                                                             |
| [VenusUsdcStrategy](https://bscscan.com/address/0x1623cb1cd01e01d0dff7e5091197a8e261fb5596)       | [vUSDC](https://bscscan.com/address/0xecA88125a5ADbe82614ffC12D0DB554E2e2867C8)                                                                                                                             |
| [VenusDaiStrategy](https://bscscan.com/address/0xc0ce366cedbe7ba63036820c72c1ea7bccd8963f)        | [vDAI](https://bscscan.com/address/0x334b3eCB4DCa3593BCCC3c7EBD1A1C1d1780FBF1)                                                                                                                              |
| [VenusBusdStrategy](https://bscscan.com/address/0x65ab000d3474dcd0fa347935dba68f0dda354c88)       | [vBUSD](https://bscscan.com/address/0x95c78222B3D6e262426483D42CfA53685A67Ab9D)                                                                                                                             |
| [Belt4BeltStrategy](https://bscscan.com/address/0xa59d8ff6c63eefc8001c8d5501bde62fca564bc6)       | [beltPair](https://bscscan.com/address/0xF6e65B33370Ee6A49eB0dbCaA9f43839C1AC04d5) [MasterBelt](https://bscscan.com/address/0xD4BbC80b9B102b77B21A06cb77E954049605E6c1)                                     |
| [DodoBusdUsdcStrategy](https://bscscan.com/address/0x466cc0484a2077b769420bec7b0620bba5ffebd1)    | [DODO](https://bscscan.com/address/0x6064DBD0fF10BFeD5a797807042e9f63F18Cfe10)                                                                                                                              |
| [DodoBusdUsdtStrategy](https://bscscan.com/address/0xd1f9f90492ad3fccf0f1772be9f0a6bdaed27e84)    | [DODO](https://bscscan.com/address/0xBe60d4c4250438344bEC816Ec2deC99925dEb4c7)                                                                                                                              |
| [DForceLendBusdStrategy](https://bscscan.com/address/0x5960f21b3e388f4435ad61cb6b74440cb93de232)  | [iBUSD](https://bscscan.com/address/0x5511b64Ae77452C7130670C79298DEC978204a47)                                                                                                                             |
| [DForceLendDaiStrategy](https://bscscan.com/address/0x1a235ea7fee8ed513c271d19f46d8a66c66aacbc)   | [iDAI](https://bscscan.com/address/0xAD5Ec11426970c32dA48f58c92b1039bC50e5492)                                                                                                                              |
| [DForceLendUsdcStrategy](https://bscscan.com/address/0xdabf728c63e50c8655bd591200cdaed850270f97)  | [iUSDC](https://bscscan.com/address/0xAF9c10b341f55465E8785F0F81DBB52a9Bfe005d)                                                                                                                             |
| [DForceLendUsdtStrategy](https://bscscan.com/address/0xf0565751ed9cf38763a34a695060536092b4aa2f)  | [iUSDT](https://bscscan.com/address/0x0BF8C72d618B5d46b055165e21d661400008fa0F)                                                                                                                             |
| [Synapse4UStrategy](https://bscscan.com/address/0x1d63e9ef24a41582b003c3908b685fa9e9655e2b)       | [SwapFlashLoan](https://bscscan.com/address/0x28ec0B36F0819ecB5005cAB836F4ED5a2eCa4D13) [Synapse MiniChef](https://bscscan.com/address/0x8F5BBB2BB8c2Ee94639E55d5F41de9b4839C1280)                          |

### Polygon

| Contrato BOC                                                                                                  | Contrato del protocolo de la tercera parte                                                                                                                                                                     |
| ------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Vault](https://polygonscan.com/address/0xd3feAe6c4fdfDE73Bd2fE99c8fE6944904DAA68A)                           |                                                                                                                                                                                                                |
| [Curve3CrvStrategy](https://polygonscan.com/address/0x1f84a8c8c31674b89a4723521ead5a48579b8bf7)               | [Curve.fi Aave Pool](https://polygonscan.com/address/0x445FE580eF8d70FF569aB36e80c647af338db351) [Curve.fi Aave Gauge](https://polygonscan.com/address/0x19793B454D3AfC7b454F206Ffe95aDE26cA6912c)             |
| [AaveUsdtStrategy](https://polygonscan.com/address/0xb80a44d494acb8db24ff7047514a16bb554290e4)                | [Aave Lending Pool V2](https://polygonscan.com/address/0x8dFf5E27EA6b7AC08EbFdf9eB090F32ee9a30fcf) [Aave Incentives Controller V2](https://polygonscan.com/address/0x357D51124f59836DeD84c8a1730D72B749d8BC23) |
| [AaveUsdcStrategy](https://polygonscan.com/address/0x5c9a02f7a45c5407bef7e98d69ca324a29803b15)                | [Aave Lending Pool V2](https://polygonscan.com/address/0x8dFf5E27EA6b7AC08EbFdf9eB090F32ee9a30fcf) [Aave Incentives Controller V2](https://polygonscan.com/address/0x357D51124f59836DeD84c8a1730D72B749d8BC23) |
| [BalancerUsdcUsdtDaiTusdStrategy](https://polygonscan.com/address/0x23c75b1397ad73b3b572ccc9c3eb3ecede9682c4) | [Balancer Vault](https://polygonscan.com/address/0xBA12222222228d8Ba445958a75a0704d566BF2C8)                                                                                                                   |
| [QuickswapDaiUsdtStrategy](https://polygonscan.com/address/0xd55001d2508b58a7bc197c50c64ebbd0ae587300)        | [StakingRewards](https://polygonscan.com/address/0xc45aB79526Dd16B00505EB39222E6B1Aed0Ef079)                                                                                                                   |
| [QuickswapUsdcDaiStrategy](https://polygonscan.com/address/0x73341635f65cb51b450288bfcca653ba4fdaa261)        | [StakingRewards](https://polygonscan.com/address/0xACb9EB5B52F495F09bA98aC96D8e61257F3daE14)                                                                                                                   |
| [QuickswapUsdcUsdtStrategy](https://polygonscan.com/address/0xa3851408642cbe4babf85514f92f06c6fcef0cdf)       | [StakingRewards](https://polygonscan.com/address/0xAFB76771C98351Aa7fCA13B130c9972181612b54)                                                                                                                   |
| [SushiUsdcUsdtStrategy](https://polygonscan.com/address/0x4717eaa5da97f11bda3a3f021a20fd8cb72eab64)           | [SushiSwap Router](https://polygonscan.com/address/0x1b02dA8Cb0d097eB8D57A175b88c7D8b47997506) [SushiSwap MiniChef](https://polygonscan.com/address/0x0769fd68dFb93167989C6f7254cd0D766Fb2841F)                |
| [SushiUsdcDaiStrategy](https://polygonscan.com/address/0xce531a4ecd1143b93dffaa054245a8f27a3e03fe)            |                                                                                                                                                                                                                |
| [Synapse4UStrategy](https://polygonscan.com/address/0x38d77bbfb522844e50dae8ec8ec62942d0de98c0)               | [SwapFlashLoan](https://polygonscan.com/address/0x85fCD7Dd0a1e1A9FCD5FD886ED522dE8221C3EE5) [Synapse MiniChef](https://polygonscan.com/address/0x7875Af1a6878bdA1C129a4e2356A3fD040418Be5)                     |
| [DodoUsdtUsdcStrategy](https://polygonscan.com/address/0x257223fcc6f33e5067260c9c18620d2f6d524b61)            | [DODO](https://polygonscan.com/address/0x813FddecCD0401c4Fa73B092b074802440544E52) [DODOMine](https://polygonscan.com/address/0xB14dA65459DB957BCEec86a79086036dEa6fc3AD)                                      |
