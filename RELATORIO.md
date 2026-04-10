# Relatório - Coelinhos da Páscoa

> [!CAUTION]
> - Lembre-se que você <ins>**não pode utilizar ferramentas de IA para
>   escrever este relatório**</ins>

## Dados do aluno

- **Cartão UFRGS**: <mark>`<preencher>`</mark>
- **Nome**: <mark>`<preencher>`</mark>

## Passos que eu segui para resolver o problema especificado (em formato de *"prompt"*)

> [!IMPORTANT]
> - Coloque aqui todas as informações necessárias para que alguém
>   (pessoa ou ferramenta de IA) possa reproduzir os seus passos para
>   solucionar o problema
> - Escreva em formato imperativo, como se fosse um *prompt* com as
>   instruções a serem seguidas na solução do problema
> - Seja objetivo e conciso: quanto *menos palavras* você utilizar,
>   melhor
> - Seja técnico e use terminologia adequada: assuma que quem irá ler
>   os seus passos possui conhecimento de Ciência da Computação e
>   Computação Gráfica
> - Caso você queira incluir informações "longas" (como algum *prompt*
>   grande usado com alguma ferramenta de IA), crie arquivos à parte e
>   adicione links no texto (por exemplo, crie o arquivo `PROMPTS.md`
>   e adicione um link markdown `[os prompts detalhados estão
>   aqui](PROMPTS.md)`)
> - Novamente, lembre-se que você *não pode utilizar ferramentas
>   de IA para escrever este relatório*

- **Leia e compreenda como funciona o código**
- **No main.cpp, altere o título da janela para 'INF01047 - 00588024 - Caio Felipe Ferreira Nunes'**
- **Crie uma funcao para a renderização dos coelhos e ovos:**
> [!RenderBunnySet(int numBunnies)]
> - Ela irá receber o número de coelhos a serem renderizados;
> - Obtenha o tempo com glfwGetTime(), defina o raio do circulo em relacao ao centro (2.0f) e o espacamento angular entre os coelhos e uma variavel M_PI com o valor aproximado de PI;
> - inicie um laco for para cada coelho;
> - calcule a defasagem (wave) baseada no índice do coelho para que pulem em tempos diferentes: 0, 90, 180, 270 graus em radianos; e a dincancia angular (offset) de cada coelho em ralacao ao 0
> - Gere a tranformacao Base dos objetos: 
> - Matrix_Rotate_Y(t * 0.5f + orbit_offset) // Gira o grupo em torno do centro do mundo
> - * Matrix_Translate(raio_mundo, 0.0f, 0.0f) // Poe o grupo no circulo de raio raio_mundo
> - * Matrix_Translate(0.0f, sin(t * 2.0f + wave) * 0.5f - 0.15f, 0.0f); // Faz o grupo "pular"
> - agora o model_bunny deve deve ficar de frente para o movimento: base_model * Matrix_Rotate_Y(-M_PI/2.0f);
> - uma a cada 4 coelhos deve dar um "mortal" : model_bunny * Matrix_Rotate_Z(t * 2.0f);
> - por fim defina a escala do coelho e desenhe ele;
> - para cada ovo multiplique a tranformacao base por:
> - * Matrix_Rotate_Z(t * 2.0f + extra_phase)    // Gira ao redor do coelho
> - * Matrix_Translate(0.0f, 0.5f, 0.0f)         // Afasta do centro do coelho
> - * Matrix_Rotate_Z(-(t * 2.0f + extra_phase)) // Contra-rotação (Billboarding)
> - * Matrix_Scale(0.1f, 0.16f, 0.1f);           // Escala
> - Desenhe os ovos
- **Compile e rode para ver o resultado** 

## Principais dificuldades encontradas durante o desenvolvimento (formato livre)

Durante o desenvolvimento do Laboratorio senti algumas difuculdades sendo as principais:
- **Entender o funcionamento do código ja fornecido:**
Tive que ler e relever o codigo e documentacao algumas vezes até entender seu funcionamento;
- **Definicao das Matrizes de tranformacao e a sua ordem:** 
como o produto matricial nao eh comutativo, a ordem em que for feita as transformacoes importam, por isso tive dificuldade na ordem em que aplicaria elas e qual usar pra gerar o resultado desejado

## Você acha que conseguiu resolver o problema de forma adequada?

Sim, o resultado final esta praticamente identico, alem disso se for necessario alterar o numero de coelhos eh necessario apenas alterar
uma constante e funcionara

## Se você quiser compartilhar mais alguma coisa, coloque aqui:

<mark>`<preencher>`</mark>

## Se você possui alguma sugestão para o professor sobre esta atividade, coloque aqui:

<mark>`<preencher>`</mark>
