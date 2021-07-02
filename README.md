<sup>| [pt](#pt) |</sup>

Because [Microsoft loves developers](https://blogs.microsoft.com/blog/2021/05/25/microsoft-loves-developers-welcome-to-build-2021), it made a solution for activating Windows available through a pre-configured server defined by the developer. It is identical to the activation system used by many Microsoft customer companies, except for the use of an open source server not licensed for commercial use. If you are a developer and are having difficulty using Windows features that depend on activation (such as Remote Desktop), follow the steps below:

_Important: Run the commands below at the prompt with administrator privileges._

_slmgr = Software Licensing ManaGeR_

1. __Register the generic product key for the version of Windows you are using (see the generic keys in the official Microsoft documentation at <https://docs.microsoft.com/en-us/windows-server/get-started/kmsclientkeys>):__

       slmgr -ipk <generic_key>

   _ipk = Install Product Key_
   
2. __Set the KMS server address:__

   _Important: The server source code is at <https://github.com/wind4/vlmcsd>. I recommend running the server on your personal domain. If you encounter difficulties, use the test server "kms.srv.crsoo.com" (don't abuse this server with too many requests)._

       slmgr -skms <kms_server_address>

   _skms = Set Key Management Service_

3. __Finally, request activation (via the server defined in the previous step):__

       slmgr -ato

   _ato = AcTivate Online_

-----------------------------

# pt

Como a [Microsoft ama os desenvolvedores](https://blogs.microsoft.com/blog/2021/05/25/microsoft-loves-developers-welcome-to-build-2021), ela disponibilizou uma solução para ativação do Windows através de um servidor pré-configurado definido pelo desenvolvedor. É idêntico ao sistema de ativação usado por muitas empresas clientes da Microsoft, exceto pelo uso de um servidor de código aberto não licenciado para uso comercial. Se você é desenvolvedor e está com dificuldades para usar recursos do Windows que dependem da ativação (como a Área de Trabalho Remota), siga os passos abaixo:

_Importante: Execute os comandos abaixo no prompt com privilégios de administrador._

_slmgr = Software Licensing ManaGeR_

1. __Registre a chave de produto genérica da versão do Windows que você está usando (veja as chaves genéricas na documentação oficial da Microsoft, em <https://docs.microsoft.com/pt-br/windows-server/get-started/kmsclientkeys>):__

       slmgr -ipk <chave_genérica>

   _ipk = Install Product Key_

2. __Defina o endereço do servidor KMS:__

   _Importante: O código fonte do servidor está em <https://github.com/wind4/vlmcsd>. Recomendo rodar o servidor em seu domínio pessoal. Caso encontre dificuldades, use o servidor teste "kms.srv.crsoo.com" (não abuse deste servidor com muitas requisições)._

       slmgr -skms <endereço_servidor_kms>

   _skms = Set Key Management Service_

3. __Por último, solicite a ativação (através do servidor definido na etapa anterior):__

       slmgr -ato

   _ato = AcTivate Online_
