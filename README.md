
# Projet SOAP avec Apache CXF

## Description
Ce projet démontre l'implémentation d'un service web SOAP avec Apache CXF, incluant une version sécurisée et non sécurisée.

## Structure du projet
- **api/** : Interface du service (`HelloService`)
- **impl/** : Implémentation du service (`HelloServiceImpl`)
- **model/** : Classes de modèle (`Person`)
- **security/** : Configuration de sécurité WS-Security (`UTPasswordCallback`)
- **Server.java** : Serveur SOAP non sécurisé
- **SecureServer.java** : Serveur SOAP sécurisé avec authentification
- **client/** : Client de test (`ClientDemo`)

## Prérequis
- Java 17
- Maven 3.x

## Compilation
```bash
mvn clean install
```

## Exécution

### Démarrer le serveur non sécurisé
```bash
mvn exec:java -Dexec.mainClass="com.acme.cxf.Server"
```
Le WSDL sera disponible sur : `http://localhost:8080/services/hello?wsdl`

### Démarrer le serveur sécurisé
```bash
mvn exec:java -Dexec.mainClass="com.acme.cxf.SecureServer"
```

### Tester avec le client
Dans un nouveau terminal :
```bash
mvn exec:java -Dexec.mainClass="com.acme.cxf.client.ClientDemo"
```

## Technologies utilisées
- Apache CXF 4.0.3
- JAX-WS
- WS-Security (WSS4J)
- Jakarta XML Binding
- Jetty (serveur embarqué)
