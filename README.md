<p align="center">
  <img src="https://raw.githubusercontent.com/jhonataT/RSA-PROJECT/master/GUI/icon.ico" height="128" />
</p>

<p align="center">
  <strong> CRIPTOGRAFIA E DESCRIPTOGRAFIA RSA: </strong>
  <br/>
  <br/>
  <a href="https://github.com/JhonataT/RSA-PROJECT"><img src="https://img.shields.io/pypi/pyversions/3?style=flat-square" alt="python"></a>
</p>

Tópicos deste projeto:
=================
<!--ts-->
   * [Sobre o projeto](#Sobre)
   * [Instalação](#instalando)
   * [Como usar](#como-usar)
   * [Funcionalidades](#Funcionalidades)
<!--te-->

<a href="#Sobre"> 
  <h1>Sobre:</h1>
  <p><strong>Alunos: Jhonata Tenório e Jorge Lucas.</strong></p>
  <p>Projeto de Criptografia RSA para a nota final da disciplina de Matemárica Discreta, Universidade Federal de Alagoas.</p>
  <p><strong>O Método RSA:</strong></p>
  <p>
    RSA <strong>(Rivest-Shamir-Adleman)</strong> é um dos primeiros sistemas de criptografia de chave pública e é 
    amplamente utilizado para transmissão segura de dados. Neste sistema de criptografia, a chave
    de encriptação é pública e é diferente da chave de decriptação que é secreta (privada).
  </p>
</a>

<a href="#instalando">
  <h1>Instalando:</h1>
  <p> 
    <strong>Instale o <a href="https://git-scm.com/downloads"> GIT </a>  e o <a href="https://www.python.org/downloads/">PYTHON3.</a></strong> 
  </p>
</a>

<p>(1.0) Abra o seu terminal e digite:</p>

```cmd
> git clone https://github.com/jhonataT/RSA-PROJECT
```

<p>(1.1) Acesse o diretório do projeto:</p>

```cmd
> cd RSA-PROJECT/GUI
```
<p>(1.2) Execute o arquivo 'script-gui.py':</p>

```cmd
> python3 script-gui.py
```

<a href="#como-usar">
  <h1>Como usar:</h1>
  <p><strong>Esolha entre três opções:</strong></p>
</a>

<!--ts-->
   * [Gerar chaves](#Gerando-chaves)
   * [Encriptar](#encriptando)
   * [Desencriptar](#desencriptando)
<!--te-->

<br/>

<a href="#gerando-chaves">
  <h2><strong>Gerando chaves:</strong></h2>
  <img src="https://user-images.githubusercontent.com/51134324/102367172-357e9880-3f98-11eb-9000-4ffd81355472.PNG" />
  <img src="https://user-images.githubusercontent.com/51134324/102369641-ef770400-3f9a-11eb-9e87-f629c44059f1.PNG" />
  <img src="https://user-images.githubusercontent.com/51134324/102369161-652ea000-3f9a-11eb-972f-32c2978886bc.PNG" />
</a>

<br/>

<a href="#encriptando">
  <h2><strong>Encriptando:</strong></h2>
  <img src="https://user-images.githubusercontent.com/51134324/102373274-c9536300-3f9e-11eb-907a-ed84b89ddbb5.PNG" />
  <img src="https://user-images.githubusercontent.com/51134324/102373914-77f7a380-3f9f-11eb-871a-1d43f677204d.PNG" />
  <br/>
  <img src="https://user-images.githubusercontent.com/51134324/102370945-6eb90780-3f9c-11eb-949f-ba55df902502.PNG" />
  <br/>
  <img src="https://user-images.githubusercontent.com/51134324/102374177-cdcc4b80-3f9f-11eb-8eed-dee2261d128c.PNG" />
</a>

<a href="#desencriptando">
  <h2><strong>Desencriptando:</strong></h2>
  <img src="https://user-images.githubusercontent.com/51134324/102392479-de87bc00-3fb5-11eb-809a-7bc92dbc1bad.PNG" />
  <img src="https://user-images.githubusercontent.com/51134324/102392892-6e2d6a80-3fb6-11eb-9350-f6390f4afac3.PNG" />
  <img src="https://user-images.githubusercontent.com/51134324/102393064-a46aea00-3fb6-11eb-9a29-cd4da932b058.PNG" />
  <br/>
  <img src="https://user-images.githubusercontent.com/51134324/102399958-07ad4a00-3fc0-11eb-8283-fca38e7e31a2.PNG" />
  <img src="https://user-images.githubusercontent.com/51134324/102393314-f1e75700-3fb6-11eb-91f0-cf401353547d.PNG" />
</a>

<br/>

<a href="#Funcionalidades">
  <h1><strong>Funcionalidades:</strong></h1>
  <p><strong>Gerar chaves:</strong></p>
</a>

```python

def generate_key():
    p = gen_prime()
    q = gen_prime()
    
    while p == q:
        q = gen_prime()
        
    n = p*q
    tot_n = phi(p, q)
    e = co_primos(tot_n)
    
```
<p><strong>
    ➥ Para gerar as chaves, usamos a função 'generate_key()' com o seguinte algoritmo:
      <p>I. Usando a função: 'gen_prime()', geramos dois primos de 32 bits ('p' e 'q');</p>
      <p>II. Com 'p' e 'q', temos 'n' ('n' = 'p' * 'q');</p>
      <p>III. Com a função: 'phi(p, q)', calculamos a função totiente de Euler [ϕ(n) = (p - 1)(q - 1)];</p>
      <p>IV. Por último, iremos usar a função 'co_primos(tot_n) para achar um inteiro 'e' tal que 1 < 'e' < 'ϕ(n)', de forma que 'e' e 'ϕ(n)' sejam co-primos.</p>
 </strong></p>


<br/>
<p><strong>Encriptar:</strong></p>

```python
def encrypt():
    n = int(e7.get())                                  # PEGANDO O VALOR DE 'n' DA ENTRADA E CONVERTENDO PARA INTEIRO.
    e = int(e8.get())                                  # PEGANDO O VALOR DE 'e' DA ENTRADA E CONVERTENDO PARA INTEIRO.
    mensagem  = scroll.get('1.0', END)                 # CAPTURANDO O TEXTO DIGITADO NA SCROLLEDTEXT.
    mensagem = mensagem.lower()                        # DEIXANDO AS LETRAS DA STRING EM MINUSCULO PARA NAO CONFLITAR COM OS DICIONARIOS.
    
    i = 0                                              # INTEIRO QUE REPRESENTA A POSICAO DA LETRA NA STRING.
    error = 0                                          # INTEIRO AUXILIAR PARA TRATAMENTO DE ERRO.
    criptografado = ""                                 # STRING INICIALMENTE VAZIA QUE GUARDA A MENSAGEM CRIPTOGRAFADA.
    while i < int(len(mensagem) - 1):
        list_int_pow = []                              # LISTA AUXILIAR GUARDA A DECOMPOSICAO EM BASE 2 DO EXPOENTE.
        
        try :
            x = dic1[mensagem[i]]
        except :
            error = -1
            break
        x = dic1[mensagem[i]]                          # VALOR DE DETERMINADO CARACTER ATRIBUIDO DE ACORDO COM O DICIONARIO.
        convert = int_bin(e, "")                       # CONVERTENDO O VALOR DE E (O EXPOENTE DA POTENCIACAO) EM BINARIO.
        generate_list_int(convert, list_int_pow)       # ARMAZENANDO EM "LIST_INT POW" OS VALORES NA BASE 2  QUE DECOMPOEM O VALOR 'e'.

        y = exp_mod_rap(list_int_pow, x, n, 1, 0)      # EXPONENCIACAO MODULAR RAPIDA PARA CRIPTOGRAFAR A MENSAGEM.
            
        criptografado = criptografado + str(y%n) +" "  # CONCATENANDO A LETRA CRIPTOGRAFADA NA STRING.
        i += 1
```

<p><strong>
    ➥ Para encriptar a mensagem, usamos a função 'encrypt()' com o seguinte algoritmo:
      <p>I. Recebemos 'n', 'e' e a 'mensagem' do usuário, convertendo o conteúdo da 'mensagem' para minúsculo;</p>
      <p>II. Usando a chave pública do destinatário 'n' e 'e' basta fazer uma potenciação modular: m^e ≡ c (mod n).

;</p>
 </strong></p>

<p><strong>Encriptar:</strong></p>
