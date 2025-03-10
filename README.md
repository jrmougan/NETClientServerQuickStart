# Explica aquí os métodos e variables dos seguintes scripts:

## HelloWorldManager.cs

### Variables

- m_NetworkManager
  Referencia ao compoñente NetworkManager para acceder as propiedades e métodos do compoñente.

### Metodos

- Awake
  Inicializa

- OnGUI
  Construe interfaz gráfica para seleccionar modo de rede

- StartButtons
  Renderiza botóns do menú para inicializar como Host, cliente ou servidor

- StatusLabels:
  Proporciona etiquetas do estado de NetworkManager

- SubmitNewPosition
  Solicita nova posición de cambio de xogador, tendo en conta que esta petición pode vir dende Servidor ou dende un dos clientes

## HelloWorldPlayer.cs

### Variables

- NetworkVariable<Vector3> Position = new NetworkVariable<Vector3>();
  Variable que obtén a posición sincronizada do xogador

### Métodos

- OnNetworkSpawn:
  Método que se chama no momento en que se instancia un novo xogador en rede

- Move:
  Se é xogador, envía petición ao servidor para cambiar de posición, se é servidor, envía solicitude a cliente para cambiar a sua posicion

- Update:
  Actualiza a posición do xogador en escea en función do valor da NetworkVariable

- GetRandomPositionOnPlane:
  Xera posición aleatoria para mover o xogador

- SubmitPositionRequestServerRpc:
  Petición RPC que utilizan os clientes para solicitudes de cambio de posición

## NetworkTransformTest.cs

### Métodos

- Update:
  Se é servidor, calcula nova posición, e actualiza a posición do transform

## RPCTest.cs

### Métodos

- OnNetworkSpawn
  Se non é servidor pero é propietario, envia chamada RPC ao servidor para inicializar a instancia de xogador

- TestClientRpc
  Chamada RPC para enviar datos a cliente

- TestServerRpc
  Chamada RPC que recibe datos de cliente

# Explica os compoñentes seguintes do GameObject `NetworkManager`:

## Network Manager

Compoñente que xestiona a configuración de rede no xogo.

## Unity Transport

Protocolo de comunicación empregado no compoñente NetworkManager, netes caso é un protocolo propio de Unity

## Hello World Manager

Script que engade ao NetworkManager a posibilidade de engadir unha interfaz gráfica para seleccionar o modo de rede, e tamen de recibir e procesar as solicitudes de, por exemplo, neste caso, as solicitudes de cambio de posición

# Explica os compoñentes seguintes do Prefab `Player`:

## Network Object

Compoñente que permite utilizar un GameObject como un obxecto en rede.

## Hello World Player

Script que controla o comportamento do Player a través de chamadas RPC

## Rpc Test

Script de proba para testear as chamadas RPC

## Network Transform

Compoñente que xestiona a sincronización dos GameObjects de rede (posición, neste caso).
