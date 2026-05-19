
# Desafio - Gerênciando instâncias EC2
Este arquivo descreve o desafio/Projeto referente ao assunto (Instâncias EC2, EBS e Bucket S3 na AWS)
## Layout APP com Load Balance e RDS/MultiAZ (Draw.io)

![App Screenshot](https://raw.githubusercontent.com/paulotobias/desafio-dio-ec2/refs/heads/main/imagens/layout-ec2-drawio.jpg)


## Documentation

### Elastic Compute Cloud (EC2)
EC2 na AWS refere-se a máquinas virtuais (VMs).
Quando você usa o EC2, você está essencialmente alugando um computador na nuvem (uma "instância") onde tem controle total sobre o sistema operacional (Linux ou Windows)

#### Instances options
    1. On-Demand - Você paga exatamente pelo que usa, por segundo ou por hora, sem compromisso de longo prazo e sem pagamento adiantado.
    2. Reserved Instances - Você assume um compromisso de fidelidade de 1 ou 3 anos para um tipo específico de instância, região e sistema operacional. Em troca, ganha um desconto massivo (que pode chegar a 72% comparado ao On-Demand).
    3. Savings Plans - É a evolução das Instâncias Reservadas. Em vez de se comprometer com uma instância específica, você se compromete com um valor monetário por hora (ex: "vou gastar $10 por hora em computação") por 1 ou 3 anos.
    4. Spot Instances - Você compra a capacidade computacional ociosa da AWS com descontos brutais de até 90%.

### Instance Types
    1. General Purpose (Uso Geral). Famílias: t3,t4g, m5,m6g
    2. Compute Optimized (Otimizadas para Computação)
    Famílias: c5, c6g, c7g
    3. Memory Optimized (Otimizadas para Memória)
    Famílias: r5, r6g, x2gd
    4. Storage Optimized (Otimizadas para Armazenamento)
    Famílias: i3, i4i, d3
    5. Accelerated Computing (Computação Acelerada / GPU)
    Famílias: p4, g5, inf1

Mais detalhes na imagem: [Instance Types](https://github.com/paulotobias/desafio-dio-ec2/blob/main/imagens/instances%20type.png)

### Elastic Block Storage  (EBS)
serviço de armazenamento em bloco de alto desempenho, projetado para ser usado com o Amazon EC2. Em termos simples, ele funciona como o "disco rígido" ou SSD da sua máquina virtual na nuvem.

Snapshots: Você pode criar "fotos" do estado do disco a qualquer momento. Esses snapshots são incrementais e ficam armazenados de forma transparente no Amazon S3, garantindo durabilidade.

### Bucket S3
serviço de armazenamento de objetos da AWS, conhecido por sua escalabilidade praticamente ilimitada, segurança e alta disponibilidade. Diferente do EBS (que é um disco rígido para uma máquina), o S3 funciona como um "repositório infinito" acessível via web.

#### Nome único.

#### Durabilidade e Disponibilidade
A Regra dos "11 Noves": O S3 foi projetado para oferecer uma durabilidade de 99,999999999%, 

Replicação Automática: Por padrão, o S3 replica seus dados em pelo menos três Availability Zones (AZs) distintas dentro da mesma região.

#### Classes de armazenamento
S3 Standard: Para dados acessados frequentemente (ex: imagens de um site).

S3 Intelligent-Tiering: Move arquivos automaticamente entre camadas de acesso conforme o uso para reduzir custos.

S3 Standard-IA (Infrequent Access): Mais barato, mas cobra por cada acesso ao arquivo. Ideal para backups.

S3 Glacier (Instant, Flexible ou Deep Archive): Para retenção de longo prazo (anos). O custo é baixíssimo, mas a recuperação pode levar de minutos a horas.

#### S3 Lifecycle Management

Define um conjunto de regras que automatizam a transição de objetos entre as diferentes classes de armazenamento ou até mesmo a exclusão definitiva deles.
Possui opção de versão.
## Authors

- [@paulopedreira](https://github.com/paulotobias)

