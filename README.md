# Solução 

  

Base A sensível seria em rds Postgres, onde o único acesso seria por chamada de api para um backend Java onde faria autenticação via token. 

Base B sensível, porém para uma leitura mais rápida, poderia ser uma cópia da base A de somente leitura. 

  

Base C, para maior rapidez das chamadas poderia ser uma base Amazon DocumentDB(Compativel com mongo), com o backend node assim conseguiria atender múltiplas requisições rest de forma simples e rápida. 

Todos os serviços com monitoração de logs via elastSearch com alertas via kibana para monitoramento de chamadas indevidas e tentativas de invasão (como bruteforce). 

  

Cada base teria seu serviço responsável por disponibilizar seus dados via rest. Porém a integração entre serviços seria por mensageria com o corpo da mensagem mais enxuto para diminuir os bytes por mensagem, e com isso também diminuiria custo e seria mais rápida a integração entre serviços
