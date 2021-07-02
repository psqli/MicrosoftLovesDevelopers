Como a Microsoft ama os desenvolvedores, ela disponibilizou uma solução para ativação do Windows através de um servidor pré-configurado definido pelo desenvolvedor. É idêntico ao sistema de ativação usado por muitas empresas clientes da Microsoft, exceto pelo uso de um servidor de código aberto não licenciado para uso comercial. Se você é desenvolvedor e está com dificuldades para usar recursos do Windows que dependem da ativação (como a Área de Trabalho Remota), siga os passos abaixo:

_Importante: Execute os comandos abaixo no prompt com privilégios de administrador._

_slmgr = Software Licensing ManaGeR_

1. __Registre a chave de produto genérica da versão do Windows que você está usando (veja as chaves genéricas na documentação oficial da Microsoft, em <https://docs.microsoft.com/pt-br/windows-server/get-started/kmsclientkeys>):__

       slmgr -ipk <chave_genérica>

   _ipk = Install Product Key_

2. __Defina o endereço do servidor KMS:__

   _Importante: O código fonte do servidor está em <https://github.com/wind4/vlmcsd>. Recomendo rodar o servidor em seu domínio pessoal. Caso encontre dificuldades, use o servidor teste "kms.srv.crsoo.com" (não abuse deste servidor com muitas requisições)._

       slmgr.vbs -skms <endereço_servidor_kms>

   _skms = Set Key Management Service_

3. __Por último, solicite a ativação (através do servidor definido na etapa anterior):__

       slmgr.vbs -ato

   _ato = AcTivate Online_
