# HubLab IRL — fork do Moblin

O Moblin ja tem tudo que voce precisa: PiP com camera dupla low-energy,
SRTLA + bonding, controle de OBS, Moblink. Este kit so poe a sua marca
nele e builda sem Mac.

## IMPORTANTE — para a live do fim de semana

**Use o Moblin normal.** O fork nao adiciona nenhuma funcao — so troca
nome e icone. Nao arrisque sua live num app recem-buildado.
Configure o PiP no Moblin hoje, faca a live, e o fork corre em paralelo.

---

## PASSO 1 — Criar o fork

1. Acesse https://github.com/eerimoq/moblin
2. Clique em **Fork** (canto superior direito)
3. Nome do repositorio: `HubLab-IRL-App`
4. Deixe **publico** (fork de repo publico; a licenca MIT permite tudo,
   inclusive uso comercial e marca propria)
5. **Create fork**

## PASSO 2 — Adicionar os 2 arquivos deste kit

No SEU fork (github.com/EvertonLopes97/HubLab-IRL-App):

1. **Add file > Upload files**
2. Arraste:
   - `codemagic.yaml`  -> tem que ficar na RAIZ
   - a pasta `branding/` (com o icon.png dentro)
3. **Commit changes**

## PASSO 3 — Buildar no Codemagic

1. Codemagic > **Add application**
2. Escolha GitHub > selecione **HubLab-IRL-App**
3. Tipo de projeto: escolha **iOS App** (NAO Flutter — este e nativo Swift)
4. Clique em **Switch to YAML configuration**
5. Deve aparecer o workflow **HubLab IRL (fork Moblin)**
6. **Start new build**

Leva uns 15-25 min (o Moblin e bem maior que nosso app Flutter).
O `HubLabIRL.ipa` chega no seu e-mail.

## PASSO 4 — Instalar

Igual ao que voce ja fez: Sideloadly no Windows + seu Apple ID gratis.
Lembre: expira em 7 dias, e voce ja tem 1 dos 3 slots ocupado pelo app
Flutter.

---

## O que este kit muda no Moblin

| O que | De | Para |
|---|---|---|
| Nome no iPhone | Moblin | HubLab IRL |
| Icone | logo do Moblin | seu icone HubLab |
| Bundle ID | com.eerimoq.Mobs | agency.hublab.irl |
| Assinatura | conta paga | `CAPABILITIES = free` (sem conta paga) |

O `Config/User.xcconfig` **nao existe no repositorio** — o Moblin espera
que cada fork crie o seu. Por isso o build gera ele automaticamente.

## LICENCA — leia

O Moblin e MIT, Copyright (c) 2023 **Erik Moqvist**. Voce pode modificar,
rebrandear e usar comercialmente. **Mas o arquivo LICENSE tem que
permanecer no repositorio** — nao apague. E o unico requisito, e e justo:
voce esta herdando anos de trabalho de graca.

## PROXIMAS FASES

- **Fase 2:** simplificar a interface (esconder o que voces nao usam,
  deixar PiP e bonding em primeiro plano)
- **Fase 3:** pre-configurar o servidor `163.176.37.123` como padrao
- **Manutencao:** de vez em quando puxar as atualizacoes do Moblin
  original (Sync fork no GitHub)

## SE O BUILD FALHAR

O ponto mais provavel: o Moblin tem varios targets (Watch, Widget, Live
Activity, Screen Recording) e algum pode reclamar de assinatura mesmo com
CODE_SIGNING_ALLOWED=NO. Me mande o erro que eu ajusto o xcodebuild.
