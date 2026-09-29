#Auditoría de red wifi insegura

Este repositorio documenta el análisis de tráfico de un sitio web que utiliza el protocolo HTTP en una red wi-fi pública. 
El objetivo es identificar los riesgos de seguridad asociados al uso de HTTP y explicar cómo una VPN mitiga dichos riesgos.

## Sitio analizado
- **URL**: http://neverssl.com
- **URL solicitada**: http://sublimesilversplendidbirds.neverssl.com/online/
- **Protocolo**: HTTP

## Evidencia observada
Al inspeccionar la pestaña **Network** de las herramientas de desarrollador del navegador se observó:

| Elemento              | Valor observado                                      |
|-----------------------|------------------------------------------------------|
| Request URL           | http://sublimesilversplendidbirds.neverssl.com/online/ 
| Request Method        | GET                                                  |
| Status Code           | 200 OK                                               |
| Host                  | sublimesilversplendidbirds.neverssl.com              |
| Protocolo             | HTTP                                                 |
| User-Agent            | Mozilla/5.0 (Windows NT 10.0; Win64; x64) ... Chrome |
| Content-Type          | text/html; charset=UTF-8                             |           

 **Importante!**: Toda esta información viaja en texto plano y puede ser interceptada por cualquier persona conectada a la misma red wifi.

## Riesgos encontrados
Al navegar por HTTP en una red wi--fi pública, un atacante puede:

- Interceptar el tráfico completo (ataque MITM).
- Ver exactamente qué sitios y páginas se visitan.
- Capturar headers, User-Agent y cualquier dato enviado.
- Modificar o inyectar contenido malicioso en las respuestas.
- Realizar ataques de phishing redirigiendo al usuario.

## Cómo ayuda una VPN
El uso de una VPN cambia radicalmente todo:

- **Cifrado**: Todo el tráfico se cifra antes de salir del dispositivo.
- **Túnel seguro**: Se crea un canal cifrado entre el cliente y el servidor VPN.
- **Protección del tráfico**: Un atacante en la red wi-fi solo ve datos cifrados e ilegibles.
- **Privacidad**: Se oculta la IP real del usuario y los destinos de navegación.

## 3 Reglas de Oro para navegar en redes wi-fi públicas

1. **Verifica siempre que se use HTTPS**  
   Asegúrate de que la URL comience con `https://` y que aparezca el candado en el navegador antes de ingresar cualquier dato sensible.

2. **Usa una VPN de confianza**  
   Activa una VPN confiable cada vez que te conectes a una red wi-fi pública. Esto cifra todo tu tráfico manteniendote seguro.

3. **Evita sitios HTTP y no envíes datos sensibles**  
   Nunca introduzcas contraseñas, datos bancarios o información personal en sitios que solo usan HTTP, especialmente en redes abiertas.
