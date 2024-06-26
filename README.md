La estructura general del proyecto se compone de los siguientes archivos: 
1. app.py: El proyecto tiene a este archivo como su punto de entrada principal. Incluye 
el bucle principal que obtiene las publicaciones de Mastodon, lleva a cabo los análisis y 
transfiere los datos a Neo4j.
2. config.py: Se utiliza este archivo para cargar la configuración del proyecto desde un 
archivo .env que contiene datos como la URI de MongoDB, el token de acceso a la API 
de Mastodon y otros detalles de configuración. 
3. mastodon.py: Este módulo se encarga de la interacción con la API de Mastodon. 
Contiene funciones para obtener los posts utilizando diferentes criterios, como hashtags 
o rangos de fechas. También incluye funciones para guardar los posts obtenidos en una 
base de datos MongoDB. 
4. analysis.py: Las funciones principales para realizar los análisis de los posts obtenidos 
están contenidas en este módulo. La biblioteca TextBlob se utiliza para analizar 
sentimientos, identificar hashtags populares, detectar comunidades y analizar contenido 
y actividad diaria con funciones incluidas. La función también incluye la generación de 
gráficos diarios de actividad utilizando la biblioteca Matplotlib. 
5. neo4j_migration.py: Los resultados del análisis son migrados a una base de datos 
Neo4j por este módulo. Usa la biblioteca py2neo para conectar con Neo4j y realizar las 
consultas Cypher requeridas para crear los nodos y relaciones correspondientes. 
6. neo4j_analysis.py: Funciones para realizar análisis adicionales utilizando la base de 
datos Neo4j son contenidas en este módulo. El sistema debe tener funciones que permitan 
analizar usuarios activos, hashtags populares, coocurrencia de hashtags, detectar 
comunidades, analizar polaridad promedio, tendencias de usuarios, influencers, temas 
discutidos y tipos de contenido. Esto permite realizar análisis más 
avanzados y obtener información adicional. 
7. analisis_extra: En esta carpeta se encuentran análisis adicionales como gráficos de la 
actividad diaria o el coeficiente de Pearson entre la polaridad y la influencia de los 
usuarios. Se implementan para análisis más visuales y claros.

La integración de las diferentes bibliotecas de Python se realiza de la siguiente manera: 
• TextBlob se utiliza en el módulo analysis.py para realizar el análisis de sentimientos 
de los posts. Esta biblioteca contribuye a lograr el objetivo específico de determinar las 
percepciones predominantes sobre el cambio climático en Mastodon. 
• pymongo se utiliza en el módulo mastodon.py para interactuar con la base de datos 
MongoDB y guardar los posts obtenidos.
• py2neo se utiliza en el módulo neo4j_migration.py para establecer la conexión con 
Neo4j y ejecutar las consultas Cypher necesarias para la migración de datos. 
• networkx se utiliza en el módulo analysis.py para crear y analizar la red social de 
usuarios. Esta biblioteca contribuye a lograr los objetivos específicos de estudiar las 
interacciones entre usuarios, detectar comunidades y analizar la propagación de 
información.
•matplotlib se utiliza en el módulo analysis.py para generar gráficos de actividad diaria. 
 
El flujo de ejecución: 
1. El archivo app.py es el punto de entrada del proyecto. 
2. Se carga la configuración desde el archivo config.py. 
3. Se obtienen los posts de Mastodon utilizando la función obtener_posts_mastodon() 
definida en app.py, que a su vez utiliza las funciones del archivo mastodon.py para 
obtener los posts y guardarlos en MongoDB. 
4. Una vez obtenidos los posts, se realiza el análisis utilizando las funciones del archivo 
analysis.py, que incluyen análisis de sentimientos, tendencias de hashtags, contenido, 
redes sociales y actividad. 
5. Los resultados del análisis se migran a una base de datos Neo4j utilizando la función 
migrate_to_neo4j() del archivo neo4j_migration.py. 
6. Se realizan análisis adicionales utilizando la base de datos Neo4j, como detección de 
comunidades, análisis de influencers y evolución de hashtags, utilizando las funciones 
del archivo neo4j_analysis.py.

Este proyecto de Python desempeña un papel fundamental en la metodología del estudio, 
ya que proporciona las herramientas y técnicas necesarias para llevar a cabo el análisis 
del discurso sobre el cambio climático en Mastodon Este enfoque integrado y basado en Python permite lograr los objetivos del estudio de manera 
eficiente y efectiva. 
