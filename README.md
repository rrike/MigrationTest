Quantum 2.1 to 3.0.1 stable MANUAL migration test.

Setup: Clean installation of Quantum 2.1 with clean URP base project. Latest Unity 6000.0.28f1, MacOS Sequioia, Rider

1. Migration fails in step Run Tools > Quantum > Migration > Import Simulation Project as QuantumMigration.cs->ImportSimulationProject function checks for .csproj file which does not exsit
2. After carefully performing following steps (after fixing 1.) project is left with multiple compilation errors that the Migration guide instructs to fix.
   However, these errors are related to namespaces including Newtonsoft and ExitGames and are located in the internally generated Quantum 3 files!

* Import Quantum3MigrationPreparation.unitypackage
* Run Quantum > Migration Preparation > Add Migration Defines
* Run Quantum > Migration Preparation > Delete Prefab Standalone Assets
* Run Quantum > Migration Preparation > Export Assets
* Run Quantum > Migration Preparation > Delete Photon
* Import Photon-Quantum-3.0.0-XXXX.unitypackage (if the Unity Editor crashes, restart Unity)
* Import Photon-Quantum-3.0.0-Stable-Migration-XXXX.unitypackage
* Restart Unity Editor (click Ignore on the Enter Safemode dialog)
* Run Tools > Quantum > Migration > Import Simulation Project
* Run Tools > Quantum > Migration > Run Initial CodeGen
* Optionally run Tools > Quantum > Migration > Run Delete Assembly Definitions
* Restart Unity Editor (click Ignore on the Enter Safemode dialog)

FULL LIST OF ERRORS:
Assets/QuantumUser/Simulation/quantum.console.runner/ChecksumVerification.cs(1,7): error CS0246: The type or namespace name 'Newtonsoft' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.runner/QuantumJsonSerializer.cs(8,7): error CS0246: The type or namespace name 'Newtonsoft' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.runner/QuantumJsonSerializer.cs(9,7): error CS0246: The type or namespace name 'Newtonsoft' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.runner/ReplayJsonSerializerSettings.cs(1,7): error CS0246: The type or namespace name 'Newtonsoft' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(13,16): error CS0101: The namespace 'Quantum' already contains a definition for 'QuantumJsonSerializer'

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(8,7): error CS0246: The type or namespace name 'Newtonsoft' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(9,7): error CS0246: The type or namespace name 'Newtonsoft' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumNetworkCommunicator.cs(1,7): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/SerializableEnterRoomParams.cs(9,23): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/AppSettings.cs(20,26): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/AppSettings.cs(19,23): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/AppSettings.cs(16,11): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/ConnectionHandler.cs(21,26): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/CustomTypesUnity.cs(19,11): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/Extensions.cs(28,26): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/Extensions.cs(27,23): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/Extensions.cs(20,11): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/FriendInfo.cs(22,26): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/FriendInfo.cs(21,23): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/FriendInfo.cs(18,11): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingClient.cs(31,26): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingClient.cs(30,23): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingClient.cs(23,11): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingPeer.cs(30,26): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingPeer.cs(29,23): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingPeer.cs(22,11): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/Player.cs(30,26): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/Player.cs(29,23): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/Player.cs(23,11): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/Region.cs(22,26): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/Region.cs(21,23): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/Region.cs(18,11): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/RegionHandler.cs(39,26): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/RegionHandler.cs(38,23): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/RegionHandler.cs(30,11): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/Room.cs(26,26): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/Room.cs(25,23): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/Room.cs(22,11): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/RoomInfo.cs(24,26): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/RoomInfo.cs(23,23): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/RoomInfo.cs(20,11): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/SupportLogger.cs(36,26): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/SupportLogger.cs(35,23): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/SupportLogger.cs(28,11): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/WebRpc.cs(24,26): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/WebRpc.cs(23,23): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/WebRpc.cs(20,11): error CS0246: The type or namespace name 'ExitGames' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/AppSettings.cs(85,16): error CS0246: The type or namespace name 'ConnectionProtocol' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingClient.cs(282,40): error CS0246: The type or namespace name 'IPhotonPeerListener' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingClient.cs(3974,22): error CS0246: The type or namespace name 'EventData' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingClient.cs(4459,26): error CS0246: The type or namespace name 'EventData' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/AppSettings.cs(98,16): error CS0246: The type or namespace name 'DebugLevel' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingPeer.cs(41,38): error CS0246: The type or namespace name 'PhotonPeer' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingClient.cs(4058,31): error CS0246: The type or namespace name 'OperationResponse' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/CustomTypesUnity.cs(48,47): error CS0246: The type or namespace name 'StreamBuffer' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/CustomTypesUnity.cs(65,50): error CS0246: The type or namespace name 'StreamBuffer' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/CustomTypesUnity.cs(88,47): error CS0246: The type or namespace name 'StreamBuffer' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/CustomTypesUnity.cs(103,50): error CS0246: The type or namespace name 'StreamBuffer' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingClient.cs(4398,38): error CS0246: The type or namespace name 'OperationResponse' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/RegionHandler.cs(142,32): error CS0246: The type or namespace name 'OperationResponse' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/CustomTypesUnity.cs(125,50): error CS0246: The type or namespace name 'StreamBuffer' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/CustomTypesUnity.cs(143,53): error CS0246: The type or namespace name 'StreamBuffer' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingPeer.cs(52,26): error CS0246: The type or namespace name 'Pool<>' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingPeer.cs(52,31): error CS0246: The type or namespace name 'ParameterDictionary' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingPeer.cs(63,34): error CS0246: The type or namespace name 'ConnectionProtocol' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingPeer.cs(74,34): error CS0246: The type or namespace name 'IPhotonPeerListener' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingPeer.cs(74,64): error CS0246: The type or namespace name 'ConnectionProtocol' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingPeer.cs(810,164): error CS0246: The type or namespace name 'ConnectionProtocol' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingPeer.cs(918,122): error CS0246: The type or namespace name 'SendOptions' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/WebRpc.cs(65,31): error CS0246: The type or namespace name 'OperationResponse' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingClient.cs(520,29): error CS0246: The type or namespace name 'EventData' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingClient.cs(530,29): error CS0246: The type or namespace name 'OperationResponse' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingClient.cs(297,16): error CS0246: The type or namespace name 'SerializationProtocol' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingClient.cs(336,16): error CS0246: The type or namespace name 'ConnectionProtocol' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingClient.cs(367,44): error CS0246: The type or namespace name 'ConnectionProtocol' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingClient.cs(691,17): error CS0246: The type or namespace name 'OperationResponse' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingClient.cs(769,36): error CS0246: The type or namespace name 'ConnectionProtocol' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingClient.cs(805,92): error CS0246: The type or namespace name 'ConnectionProtocol' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingClient.cs(2178,122): error CS0246: The type or namespace name 'SendOptions' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingClient.cs(2334,46): error CS0246: The type or namespace name 'OperationResponse' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.runner/ReplayJsonSerializerSettings.cs(5,19): error CS0246: The type or namespace name 'JsonSerializerSettings' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingClient.cs(2562,41): error CS0246: The type or namespace name 'DebugLevel' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingClient.cs(2590,46): error CS0246: The type or namespace name 'OperationResponse' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingClient.cs(2623,49): error CS0246: The type or namespace name 'OperationResponse' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.runner/QuantumJsonSerializer.cs(13,48): error CS0234: The type or namespace name 'JsonAssetSerializerBase' does not exist in the namespace 'Quantum' (are you missing an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(13,48): error CS0234: The type or namespace name 'JsonAssetSerializerBase' does not exist in the namespace 'Quantum' (are you missing an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingClient.cs(2952,45): error CS0246: The type or namespace name 'StatusCode' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingClient.cs(3182,37): error CS0246: The type or namespace name 'EventData' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumNetworkCommunicator.cs(9,45): error CS0535: 'QuantumNetworkCommunicator' does not implement interface member 'ICommunicator.OnDestroyAsync()'

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumNetworkCommunicator.cs(9,45): error CS0535: 'QuantumNetworkCommunicator' does not implement interface member 'ICommunicator.ActorNumber'

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingClient.cs(3377,50): error CS0246: The type or namespace name 'DisconnectMessage' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.runner/QuantumJsonSerializer.cs(16,19): error CS0246: The type or namespace name 'JsonSerializer' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumNetworkCommunicator.cs(19,14): error CS0246: The type or namespace name 'ByteArraySlice' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(16,19): error CS0246: The type or namespace name 'JsonSerializer' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumNetworkCommunicator.cs(23,20): error CS0246: The type or namespace name 'EventData' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.runner/QuantumJsonSerializer.cs(34,20): error CS0246: The type or namespace name 'JsonSerializerSettings' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(34,20): error CS0246: The type or namespace name 'JsonSerializerSettings' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.runner/QuantumJsonSerializer.cs(14,22): error CS0246: The type or namespace name 'JsonSerializer' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(14,22): error CS0246: The type or namespace name 'JsonSerializer' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingClient.cs(769,66): error CS0103: The name 'ConnectionProtocol' does not exist in the current context

Assets/QuantumUser/Simulation/quantum.console.spectator/PhotonLoadbalancingApi/LoadBalancingClient.cs(805,122): error CS0103: The name 'ConnectionProtocol' does not exist in the current context

Assets/QuantumUser/Simulation/quantum.console.runner/QuantumJsonSerializer.cs(43,46): error CS0246: The type or namespace name 'JsonConverter' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(43,46): error CS0246: The type or namespace name 'JsonConverter' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.runner/QuantumJsonSerializer.cs(78,39): error CS0246: The type or namespace name 'JsonReader' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.runner/QuantumJsonSerializer.cs(78,97): error CS0246: The type or namespace name 'JsonSerializer' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(78,39): error CS0246: The type or namespace name 'JsonReader' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(78,97): error CS0246: The type or namespace name 'JsonSerializer' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.runner/QuantumJsonSerializer.cs(111,38): error CS0246: The type or namespace name 'JsonWriter' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.runner/QuantumJsonSerializer.cs(111,71): error CS0246: The type or namespace name 'JsonSerializer' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(111,38): error CS0246: The type or namespace name 'JsonWriter' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(111,71): error CS0246: The type or namespace name 'JsonSerializer' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.runner/QuantumJsonSerializer.cs(139,45): error CS0246: The type or namespace name 'JsonWriter' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(139,45): error CS0246: The type or namespace name 'JsonWriter' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.runner/QuantumJsonSerializer.cs(160,44): error CS0246: The type or namespace name 'JsonReader' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(160,44): error CS0246: The type or namespace name 'JsonReader' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.runner/QuantumJsonSerializer.cs(207,40): error CS0246: The type or namespace name 'JsonConverter' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(207,40): error CS0246: The type or namespace name 'JsonConverter' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.runner/QuantumJsonSerializer.cs(213,39): error CS0246: The type or namespace name 'JsonReader' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.runner/QuantumJsonSerializer.cs(213,97): error CS0246: The type or namespace name 'JsonSerializer' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(213,39): error CS0246: The type or namespace name 'JsonReader' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(213,97): error CS0246: The type or namespace name 'JsonSerializer' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.runner/QuantumJsonSerializer.cs(241,38): error CS0246: The type or namespace name 'JsonWriter' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.runner/QuantumJsonSerializer.cs(241,71): error CS0246: The type or namespace name 'JsonSerializer' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(241,38): error CS0246: The type or namespace name 'JsonWriter' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(241,71): error CS0246: The type or namespace name 'JsonSerializer' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.runner/QuantumJsonSerializer.cs(260,52): error CS0246: The type or namespace name 'DefaultContractResolver' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(260,52): error CS0246: The type or namespace name 'DefaultContractResolver' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.runner/QuantumJsonSerializer.cs(262,74): error CS0246: The type or namespace name 'MemberSerialization' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.runner/QuantumJsonSerializer.cs(262,32): error CS0246: The type or namespace name 'JsonProperty' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(262,74): error CS0246: The type or namespace name 'MemberSerialization' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(262,32): error CS0246: The type or namespace name 'JsonProperty' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.runner/QuantumJsonSerializer.cs(267,73): error CS0246: The type or namespace name 'MemberSerialization' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.runner/QuantumJsonSerializer.cs(267,26): error CS0246: The type or namespace name 'JsonProperty' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(267,73): error CS0246: The type or namespace name 'MemberSerialization' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(267,26): error CS0246: The type or namespace name 'JsonProperty' could not be found (are you missing a using directive or an assembly reference?)

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(16,34): error CS0111: Type 'QuantumJsonSerializer' already defines a member called 'CreateSerializer' with the same parameter types

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(20,31): error CS0111: Type 'QuantumJsonSerializer' already defines a member called 'FromJson' with the same parameter types

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(27,31): error CS0111: Type 'QuantumJsonSerializer' already defines a member called 'ToJson' with the same parameter types

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(34,43): error CS0111: Type 'QuantumJsonSerializer' already defines a member called 'CreateSettings' with the same parameter types

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(44,28): error CS0111: Type 'QuantumJsonSerializer.FixedSizeBufferConverter' already defines a member called 'CanConvert' with the same parameter types

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(61,20): error CS0111: Type 'QuantumJsonSerializer.FixedSizeBufferConverter' already defines a member called 'GetFixedBufferElementType' with the same parameter types

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(78,30): error CS0111: Type 'QuantumJsonSerializer.FixedSizeBufferConverter' already defines a member called 'ReadJson' with the same parameter types

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(111,28): error CS0111: Type 'QuantumJsonSerializer.FixedSizeBufferConverter' already defines a member called 'WriteJson' with the same parameter types

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(139,27): error CS0111: Type 'QuantumJsonSerializer.FixedSizeBufferConverter' already defines a member called 'WriteJsonArray' with the same parameter types

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(160,27): error CS0111: Type 'QuantumJsonSerializer.FixedSizeBufferConverter' already defines a member called 'ReadJsonArray' with the same parameter types

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(209,28): error CS0111: Type 'QuantumJsonSerializer.ByteArrayConverter' already defines a member called 'CanConvert' with the same parameter types

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(213,30): error CS0111: Type 'QuantumJsonSerializer.ByteArrayConverter' already defines a member called 'ReadJson' with the same parameter types

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(241,28): error CS0111: Type 'QuantumJsonSerializer.ByteArrayConverter' already defines a member called 'WriteJson' with the same parameter types

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(262,46): error CS0111: Type 'QuantumJsonSerializer.WritablePropertiesOnlyResolver' already defines a member called 'CreateProperties' with the same parameter types

Assets/QuantumUser/Simulation/quantum.console.spectator/QuantumJsonSerializer.cs(267,39): error CS0111: Type 'QuantumJsonSerializer.WritablePropertiesOnlyResolver' already defines a member called 'CreateProperty' with the same parameter types

