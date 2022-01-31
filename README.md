# CRUD-SPRING-BOOT
***
Dependencias:
- Data-JPA
- Spring-WEB
- OpenFeign 
- H2DataBase

### Esse é CRUD feito com Java e SpringBoot. Utilizando algumas dependências como JPA, SpringWeb e OpenFeign. 

O projeto tem um server local onde tem alguns dos metodos de requisiçao HTTP, como GET, PUT, DELETE etc.
onde usamos uma interface swagger para fazer a requisicao.
***

temos duas classes **Cliente** e **Endereco**, que são onde ficam meus __atributos__ juntamente com algumas anotações do framework **SpringBoot** como:

__@Id__ -> informa que aquele atributo tem quer uma numeração unica para cada objeto criado.

__@GeneratedValue__ -> Significa que vai ser gerado um valor automatico.

__@ManyToOne__ -> Significa que aquele atributo é de Muitos para Um
***

temos duas interface de serviço que são a __ClienteService__ e __ViaCepService__:

__ClienteService__ -> onde vai ter todos os metodos que vao ser utilizados para a requisiçao

__ViaCepService__ -> tem o __@FeignCliente__ que esta criando minha interface central com name e url.
tem o metodo __consultaCep__ que como o nome ja diz, vai consultar o cep aparti do paramentro String cep.

E dentro do package __impl__ temos a classe __ClienteServiceImpl__:
que vai implementar meus metodos da interface __ClienteService__ junto com as regras de negocios. 
***

temos a classe __ClienteRestController__:

__@RestController___ que significa, que aquela classe esta usando serviços REST, ou seja é um controlador REST.

__@RequestMapping("clientes")__ que é a URI de onde o controlador sera usado.

__@Autowired__ que vai fazer a injençao de dependencias da minha classe ClienteService

e a classe tambêm tem os metodos do __ClienteService__ só que com as anotacoes dos metodos REST para acesso a WEB.
