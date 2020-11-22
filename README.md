# Tutorial de Windows Server  
   
- Disciplinas: Gestão de Sistemas Operacionais  
- Professor Leandro Leandro Vasconcelos Reis  
  
- Autores:  
[Felipe Macchi Zadorosny](https://github.com/FelipeMacchiz)  
[Gustavo da Silva Pereira](https://github.com/GuxtaGol)  
[Lucas Damião Martini](https://github.com/lDamiaol)  
[Matheus de Souza Zampieri]()  
  
### Configurar as máquinas virtuais  

Depois de instalada, para fazer a
configuração da sua máquina você precisa ir até o Virtual Box, clicar em na maquina
que você quer configurar, selecionar as configurações, dar um nome a ela, clicar em
próximo, selecionar o tamanho de memória que você quer dar a ela, marcar criar um
disco rígido virtual agora, próximo, selecionar VDI (VirtualBOX Disk Image), próximo,
marcar Dinamicamente alocado, próximo, selecionar o tamanho que você deseja dar
ao disco e clicar em criar.

## Configurar a rede IPV4 de forma manual  

Desabilitamos o Firewall
depois de desabilitado ir centro de rede compartilhamentos em seguida gerência
conexão de rede dentro de conexão local ir em propriedades, clicar protocolo TCP/IP
versão 4 (TCP/IPv4) duplo click e colocar usar a seguinte endereço IP, colocando em
endereço IP: 192.168.20.1, máscara de sub-rede: 255.255.255.0 e gateway padrão:
192.168.20.1 ! Feito isso colocar trabalho e voltar para centro de rede e ativar
descoberta de rede, ativar compartilhar de arquivos, compartilhar pasta pública, ativar
compartilhamento para que qualquer pessoa com acesso a rede possa abrir, e alterar
arquivos, compartilhamento de impressão pode deixar desativado. Indo para Windows
XP ir para painel de controle altere para modo de exibição clássico ir para sistema e
dentro do sistema alterar grupo de trabalho para workgroup reiniciar a máquina, em
seguida desativar firewall do Windows ir em conexão de rede, propriedades e usar o
endereço 192.168.20.2 máscara de sub-rede: 255.255.255.0 e gateway padrão:
192.168.20.1 ir em promp de comando para verificar se a rede está conversando uma
com a outra colocado ping 192.168.20. 1. 

## Configurar o nome de cada computador  

 Iniciar, painel de controle,
sistema, Alterar configurações, alterar e vai aparecer uma aba com nome do
computador, você retira o que está ali, adiciona o nome que você desejar, clique em
ok e então ele vai pedir para reiniciar o computador. 

## Configurar o acesso remoto ao Server  

No Windows XP, iniciar, meu
computador, meus locais de rede a pasta virtual já vai estar aparecendo, como Virtual em
Servidor, a parte de pastas compartilhadas já está pronta. Agora no Windows 2k8, iniciar,
painel de controle, contas de usuário, gerenciar outra conta, criar outra conta no modo
administrador, entrar na conta criada e adicionar uma senha, criar uma conta padrão e
adicionar uma senha. Iniciar, painel de controle, alterar configurações, na opção remota,
selecionar “permitir conexões… (menos seguro)”, selecionar o usuário, adicionarNesta 
caixa adicionar o nome da conta administrador e clicar em verificar, ok, ok novamente,
aplicar e ok. No Windows XP, iniciar, todos os programas, acessórios, conexão de área de
trabalho remoto, “Opções >>”, na área computador adicionar o IP 192.168.20.1, nome do
usuário colocar o administrador, conectar assim você terá acesso total a outra máquina. 

## Configurar DNS  

Depois de instalada a DNS clicar em iniciar , clicar em
ferramentas administrativas, DNS, servidor, zona de pesquisa direta, clicar com o
botão direito, clicar em nova zona, depois de clicar em nova zona, clicar em avançar,
zona primária, dar o nome da zona do mesmo nome que foi dado o servidor, avançar,
não alterar o nome do arquivo dns, avançar, não permitir atualizações dinâmicas,
avançar e concluir.
Clicar em zona de pesquisa inversa , nova zona, avançar , zona primária, avançar,
zona de pesquisa Inversa IPv4, avançar, digitar o endereço IP que está sendo usado,
avançar, avançar novamente, não permitir atualizações dinâmicas, avançar e concluir.
Para concluir dar um duplo clique e abrir o arquivo que foi criado dentro de zona de
pesquisa direta, clicar com o botão direito, clicar em novo Host (A ou AAAA), deixar em
branco o nome, e apenas adicionar o endereço IP, clicar em Criar registro de ponteiro
associado (PTR) e adicionar Host, concluído.
Clicar com o botão direito novamente, Novo alias (CNAME), digitar no Nome do alias
WWW e ele ira aparecer o nome do servidor, clicar em procurar, servidor, zona de
pesquisa direta, ate chegar no ultimo arquivo e depois clicar em OK e OK novamente.

## Configurar DHCP  

Clicar em gerenciador de servidores , funções , adicionar
funções, próximo, marcar o DHCP, próximo, próximo , próximo novamente, digitar no
domínio pai o nome do servidor, clicar em validar, próximo, marcar o WINS não é
necessário aos aplicativos dessa rede, próximo , adicionar, colocar o nome do escopo
de Geral, adicionar o endereço IP inicial e o final, colocar a máscara de Sub-rede
padrão ex “255.255.255.0”, colocar o Gateway padrão ex “192.168.20.1”, e clicar em
OK, próximo, marcar o Desabilitar o modo sem monitoração do estado DHCPv6 para
este servidor ..., próximo e instalar. 

## Configurar ISS  

Clicar em gerenciador de servidores , funções , adicionar funções,
próximo, marcar o Servidor Web (IIS), adicionar recursos necessários, próximo,
próximo novamente, marcar o Redirecionamento HTTP, marcar o Desenvolvimento de
aplicativo, marcar todo Ferramentas de gerenciamento, marcar o Servidor de
Publicação FTP, próximo, e clicar em instalar. 

## Configurar FTP  

: Depois de criar o FTP ir em iniciar, ferramentas administrativas,
Gerenciador do Serviços de informações da internet (IIS) 6.0, Servidor, abrir pasta que
esta dentro do servidor, clicar com o botão direito na parte em branco que está dentro
da pasta, clicar em novo, site FTP, avançar, na descrição você coloca o caminho do seu
site exemplo “ftp.aula.com”, avançar, digite o endereço IP da maquina e deixe a porta
padrão como 21 e a 22, avançar, marcar o não isolar usuários, avançar, clique em
procurar e encontre a pasta do seu servidor , avançar, marcar leitura e gravação,
avançar e concluir. 

## Configurar Internet Local para o Server (NAT Externo)  

No virtual
Box, selecionar o Windows Server, em configurações, rede, adaptador 2, habilitar 
placa de rede e no campo "Conectado a:" selecionar NAT assim estará acrescentando
uma nova placa de rede, apos isso rodar a maquina.No virtual Box, selecionar o
Windows Server, em configurações, rede, adaptador 2, habilitar placa de rede e no
campo "Conectado a: " selecionar NAT assim estará acrescentando uma nova placa de
rede, apos isso rodar a maquina.

## Configurar Internet para clientes do Server (NAT Interno)  

 Com
a maquina aberta vão em iniciar, painel de controle, centro de rede, gerenciar
conexões de rede, para facilitar é bom renomear as conexões de rede, a primeira
como interna e a segunda como externa ou de sua preferência, gerenciador de tarefas,
configurar ESC do IE, mascar a opção desligada nas duas opções, no Explorer baixar o
Fire Fox.
 Em gerenciador de servidores, em funções, adicionar funções , em Serviços de Acesso
de Diretiva de Rede, próximo, próximo novamente , marcar a caixa Serviços de
Roteamento e Acesso Remoto , próximo e instalar. Após a instalação, fecha essa aba,
vai em iniciar, Ferramentas Administrativas, Roteamento e acesso remoto, para ativar
o serviço clica com o botão direito em servidor e em "Configurar e Habilitar
Roteamento e Acesso Remoto", avançar, selecionar a segunda caixa "Conversão de
endereço de rede (NAT)... ", avançar, agora onde vc nomeou anteriormente como rede
interna, rede externa ou de sua preferência, selecione a rede externa, avançar e
concluir.
Você verá que apareceu algumas opções no seu serviço isso significa que ele esta
ativo. Agora no Windows XP já esta funcionando a internet, porém o Explore é um
browser muito lento, você pode usar aquela pasta compartilhada para passa o
instalador do FireFox (browser mais recomendado) ou baixar pelo Explore mesmo.
Assim tendo acesso a internet para as duas maquinas virtuais.



