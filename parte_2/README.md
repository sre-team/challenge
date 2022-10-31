# Perfil de desenvolvimento:

**Objetivo:** Desenvolver uma aplicação capaz de executar requisições na [api rest do github](https://docs.github.com/en/rest).

**Requisitos**:
- Utilizar a linguagem de programação Golang ou Python no processo de desenvolvimento.
- Todo o processo de construção e entrega deve ser baseado nas práticas descritas no Twelve Factory, consulte a URL: [https://12factor.net/](https://12factor.net/).


**Funcionalidade:**
* A aplicação deverá expor uma API REST que receba como input o nome de um usuário do github e traga os seguintes dados:
    - Últimas contribuições "commits" do usuário;
    - Relação de projetos disponíveis em ordem alfabética;

* O ["deployment"](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) da aplicação deve utilizar encapsulamento no formato de container e estrutura de deployment preparada para entrega em ambiente de microserviços, preferencialmente Kubernetes, se possível publicar a imagem em um repositório público ou fornecer informações para o build do Dockerfile.

* Para o consumo e consulta destes dados, você poderá escolher entre duas opções: Documentar adequadamente a sua API usando o próprio repositório ou um padrão comum aceito como o [swagger](https://swagger.io) ou criar uma página em uma linguagem de sua preferência que seja capaz de chamar a API e mostre os resultados, em ambos os cenários você deverá prever o modelo de yaml para construção dos resources que permitirão acessar o serviço em uma plataforma kubernetes para a consulta mas não é necessário efetivamente expor e manter uma plataforma no ar.

* Não se esqueça de garantir a disponibilidade da aplicação usando processos como a provisão de uma URL de checagem de saúde "/health" ou similar configurada devidamente para que a plataforma de orquestração usada consiga detectar uma falha na aplicação ou na comunicação com o github por exemplo, e de expor métricas de execução utilizando formato e padrão de sua escolha que podeia ser consumido por uma ferramenta de monitoração (por exemplos, Prometheus, Zabbix, Cloudwatch da AWS, Stackdriver da google ou similar).

**Importante:** Não é necessário configurar o processo de autenticação para acesso a repositórios privados, considere como primicia que o usuário submetido na requisição possui uma conta pública no github, ficará a seu critério determinar o formato ideal de output para as requisições submetidas trazendo os dados solicitados.


---

Sinta-se a vontade para abrir issues no repositório caso ocorra dúvidas sobre o que deve ser feito e quais as expectativas da equipe sobre o seu trabalho.
