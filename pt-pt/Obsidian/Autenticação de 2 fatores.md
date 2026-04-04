---
permalink: 2fa
---
Se tiver uma [conta Obsidian](https://obsidian.md/account) pode ativar a autenticação de dois fatores (2FA) para proteger a sua conta com uma segunda etapa de verificação.

## Ativar a 2FA

- Inicie sessão na [sua conta Obsidian](https://obsidian.md/account/profile) a partir do seu browser.
- Na secção **Perfil**, aceda a **Autenticação de 2 fatores** e selecione **Ativar**.
- Aparecerá uma janela de popup a pedir-lhe que conecte uma aplicação de autenticação com um **código QR** ou uma **chave de configuração**.

> [!hint]- Aplicações de autenticação populares
> - [Authy](https://authy.com)
> - [Google Authenticator](https://play.google.com/store/apps/details?id=com.google.android.apps.authenticator2)
> - [Microsoft Authenticator](https://www.microsoft.com/en-us/security/mobile-authenticator-app)
> - [iCloud Keychain](https://support.apple.com/en-gb/guide/iphone/ipha6173c19f/ios)

- Depois de conectada, a sua aplicação de autenticação fornecer-lhe-á um código de seis dígitos. Introduza esse código abaixo da secção **código QR/chave de configuração**, no passo 3.
- Por fim, introduza a sua palavra-passe atual.
- Selecione **Concluir configuração**.
- A janela de popup será substituída por uma janela de confirmação com os seus códigos de recuperação. Por favor, descarregue os seus códigos de recuperação, pois precisará deles para desbloquear a sua conta.

A sua 2FA está agora configurada.

> [!warning]- Cópias de segurança do código QR/chave de configuração
> Se decidir guardar uma cópia de segurança do seu **código QR** ou **chave de configuração** além dos seus códigos de recuperação, recomendamos vivamente que a guarde num sistema com encriptação por palavra-passe.

## Gerar códigos de recuperação

Se ativou a 2FA antes de os códigos de recuperação estarem disponíveis, ou se pretender atualizar os seus códigos de recuperação, siga estes passos:

- Inicie sessão na [sua conta Obsidian](https://obsidian.md/account/profile) a partir do seu browser.
- Junto à autenticação de 2 fatores, selecione **Atualizar códigos de recuperação**.
- Na janela de popup, introduza a sua **palavra-passe** e o **código de autenticação de 6 dígitos**.
- Uma janela de confirmação mostrará os seus códigos de recuperação. Tem duas opções:
    - **Copiar códigos de recuperação**: Copie os códigos para colar noutro local.
    - **Descarregar códigos de recuperação**: Descarregue um ficheiro `obsidian-recovery-codes.txt` com os seus códigos.
- Selecione **Percebido** para fechar a janela de popup.

Pode usar um código de recuperação **uma vez** em vez do seu **código de autenticação de 6 dígitos**. Também pode atualizar os seus códigos de recuperação a qualquer momento.

## Desativar a 2FA

- Inicie sessão na [sua conta Obsidian](https://obsidian.md/account/profile) a partir do seu browser.
- Na secção **Perfil**, aceda a **Autenticação de 2 fatores** e selecione **Desativar**.
- Introduza a sua palavra-passe do Obsidian.
- Introduza o código atual de seis dígitos da sua aplicação de autenticação.
- Selecione **Desativar 2FA**.
- Será levado de volta ao ecrã de gestão de conta.

A definição de **Autenticação de 2 fatores** voltará a mostrar um botão **Ativar**, indicando que a 2FA foi desativada.

## Perguntas frequentes

**Ativei a 2FA. Serei desconectado dos meus dispositivos Obsidian atuais?**
Não. Ativar a 2FA não o desconecta em todo o lado por sua conveniência. Se necessário, pode fazê-lo manualmente a partir da sua página de conta e, subsequentemente, iniciar sessão novamente em cada um dos seus dispositivos.

**Ativei e depois desativei a 2FA. Gostaria de a configurar novamente. Posso usar o código QR ou chave de configuração original?**
Não. Ser-lhe-á fornecido um novo **código QR** e uma nova **chave de configuração** sempre que iniciar uma nova configuração de 2FA.

**Ativei a 2FA. Ainda não me foi pedida após várias tentativas de sair/entrar. Está a funcionar?**
A cache do seu browser pode estar a permitir-lhe parecer que está a fazer alterações na página (como iniciar ou terminar sessão) quando na realidade está a aceder aos dados guardados. Tente usar uma janela de navegação privada para iniciar sessão e confirmar que a 2FA está a funcionar.

Se continuar a ter este comportamento, por favor [submeta um relatório de erro](https://forum.obsidian.md/c/bug-reports/7).

**Perdi os meus códigos de recuperação, aplicação de autenticação e tudo o que preciso para iniciar sessão na minha conta. O que devo fazer?**

Se perdeu os seus códigos de recuperação e a aplicação de autenticação, envie um email para [support@obsidian.md](mailto:support@obsidian.md?subject=I%20lost%20my%202FA) para obter assistência no acesso à sua conta.
