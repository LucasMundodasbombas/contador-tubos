# Contador de Tubos

Aplicativo web para contar tubos numa carga a partir de uma foto. Ele encontra a boca de cada tubo, numera e mostra o total. Funciona no navegador do celular, sem instalar nada, e pode ser adicionado à tela inicial.

## Como usar

1. Abra o app no celular e toque em **Tirar ou escolher foto**.
2. Confira os números. Use **Adicionar** para marcar um tubo que ficou de fora e **Excluir** para tirar uma marcação errada.
3. Se a foto pegar muita coisa além da pilha, use **Área** e arraste um retângulo em volta dos tubos.
4. Toque em **Gerar imagem final** e segure a imagem para salvar ou compartilhar.
5. Dê um nome (placa, nota fiscal) e toque em **Registrar contagem** para guardar no histórico do aparelho.

Dicas para a foto: tire de frente para a pilha, com a pilha ocupando a maior parte da imagem e sem sombra forte.

## Como funciona

Todo o processamento acontece no próprio celular, em JavaScript puro (`index.html`). Nenhuma foto é enviada para a internet.

- A foto é convertida para tons de cinza e os contornos são detectados (Canny).
- Uma transformada de Hough procura círculos. O tamanho do tubo é descoberto sozinho, testando vários tamanhos e escolhendo o que forma o maior grupo de círculos encostados.
- Círculos soltos, longe da pilha, são descartados.

## Publicação

O site é publicado pelo GitHub Pages a partir da branch `main`.
