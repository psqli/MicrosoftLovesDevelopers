Because [Microsoft loves developers](https://blogs.microsoft.com/blog/2021/05/25/microsoft-loves-developers-welcome-to-build-2021), it made a solution for activating Windows available through a pre-configured server defined by the developer. It is identical to the activation system used by many Microsoft customer companies, except for the use of an open source server which is not licensed for commercial use. If you are a developer and are having difficulty using Windows features that depend on activation (such as Remote Desktop), follow the steps below:

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
