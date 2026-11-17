---
title: "Lição 12 - Publique o site com o GitHub Pages"
description: "Use o aplicativo GitHub Copilot para configurar um fluxo de trabalho do Pages, revisar a pull request e verificar o Space Quiz publicado."
authors:
  - jamesmontemagno
lastUpdated: 2026-10-12
---

Publique o Space Quiz com o GitHub Pages para que todos possam acessá-lo. O Copilot pode preparar o fluxo de trabalho e orientar a implantação, mas você deve revisar as alterações e confirmar que o site está no ar.

Nesta lição, você vai:

- pedir ao Copilot para configurar a publicação com o GitHub Pages.
- revisar o fluxo de trabalho e a pull request antes de fazer merge.
- acompanhar a implantação e verificar o site publicado.

## Cenário

O Space Quiz já está em um repositório do GitHub, mas ainda é preciso oferecer uma forma simples de experimentá-lo. Publicar o site de arquivo único com o GitHub Pages disponibiliza uma URL pública sem adicionar um servidor ou uma dependência de runtime.

## Peça ao Copilot para preparar a publicação

> [!WARNING]
> Criar uma pull request pode confirmar e enviar código. Revise as configurações de aprovação e o repositório de destino antes de enviar este prompt. Com **Approve all**, não conte com a exibição de uma confirmação separada.

Na sessão do aplicativo Copilot para `space-quiz`, envie este prompt:

```plaintext
Prepare a publicação deste repositório com o GitHub Pages. Crie um fluxo de trabalho do GitHub Actions que compile o site, se necessário, e faça a implantação no GitHub Pages depois que as alterações chegarem à branch padrão. Se ainda não houver um README, adicione um com a descrição do aplicativo e as instruções para executá-lo localmente. Crie uma pull request com essas alterações e informe o link e quaisquer configurações ou permissões necessárias do Pages. Não faça merge, não habilite o merge automático, não altere as configurações do Pages nem faça a implantação. Pare e aguarde minha revisão.
```

## Revise o fluxo de trabalho e a pull request

1. Confirme se o README só foi adicionado caso ainda não existisse no repositório.
2. Revise as alterações da pull request, incluindo as etapas de build e implantação do fluxo de trabalho, os gatilhos e as permissões.
3. Confirme se o fluxo de trabalho publica a partir da branch padrão, e não de uma pull request que ainda não foi integrada.
4. Solicite as correções necessárias e revise o diff atualizado. Aguarde a aprovação nas verificações obrigatórias da pull request antes de autorizar o merge.

## Autorize o merge e a implantação

> [!WARNING]
> O prompt a seguir autoriza o agente a fazer merge da pull request revisada, alterar as configurações do Pages no repositório e publicar o site. Envie-o somente depois de concluir a revisão e confirmar o repositório e a pull request. Dependendo das configurações de aprovação, essas ações podem ocorrer sem outra confirmação.

Substitua `<PR_NUMBER>` pelo número da pull request revisada e envie este prompt separadamente:

```plaintext
Revisei a pull request <PR_NUMBER> neste repositório e autorizo o merge e a implantação. Habilite o GitHub Pages usando o GitHub Actions, faça o merge dessa pull request somente depois que todas as verificações obrigatórias forem aprovadas e acompanhe a implantação até a conclusão. Informe a URL final do site publicado. Se não tiver permissão para habilitar o Pages ou fazer o merge, diga exatamente o que preciso aprovar ou fazer; não informe que a implantação foi concluída até que o site esteja no ar.
```

![Diagrama em três etapas: uma pull request do space-quiz integrada; uma execução bem-sucedida de Deploy website no GitHub Actions com as etapas Build website, Upload artifact e Deploy to Pages; e o Space Quiz publicado em yourname.github.io/space-quiz/.](../../../_images/first-steps-app-pages-deploy.svg)

## Verifique a implantação

1. Acompanhe a execução de implantação do GitHub Actions até que ela seja concluída com êxito.
2. Abra a URL informada e confirme que o Space Quiz carrega.

Se o agente não puder habilitar o Pages ou fazer merge da pull request, siga as instruções específicas fornecidas. Não considere a tarefa concluída até que a implantação seja bem-sucedida e o site esteja no ar.

## Resumo e próximos passos

O Space Quiz agora está disponível como um site, e você verificou a implantação em vez de confiar apenas no relato do agente. Continue para a [Lição 13: Revisão e próximos passos][next-lesson].

[next-lesson]: ../13-review/
