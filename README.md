# Criando-o-Seu-Primeiro-Token-do-Zero

Vamos dividir o processo em módulos para facilitar o entendimento:

### Módulo 1: Configuração da Wallet Metamask e RPC Info
Antes de criar seu token, você precisa configurar uma carteira digital e conectar-se à rede blockchain. A carteira Metamask é amplamente utilizada para interagir com a Ethereum blockchain e outras compatíveis.

1. **Instalação da Metamask**: Baixe e instale a extensão Metamask para o seu navegador.
2. **Criação de uma nova carteira**: Siga as instruções para criar uma nova carteira. Anote a frase de recuperação em um local seguro.
3. **Conexão com a rede**: Conecte-se à rede de sua escolha adicionando as informações de RPC. Isso pode ser feito nas configurações da Metamask, na seção "Redes".

### Módulo 2: Utilizando a IDE REMIX
A REMIX é uma IDE poderosa para desenvolvimento de smart contracts na Ethereum blockchain.

1. **Acesso à REMIX**: Acesse [REMIX IDE](^7^) e crie um novo arquivo para o seu contrato.
2. **Escrevendo o contrato**: Utilize Solidity para escrever o contrato do seu token. Você pode começar com um contrato simples que define o nome, símbolo e quantidade total do token.
3. **Compilação**: Compile seu contrato na REMIX para verificar se há erros.

### Módulo 3: Deploy do Token
Após escrever e compilar seu contrato, é hora de implantá-lo na blockchain.

1. **Conectar a Metamask**: Na REMIX, conecte sua carteira Metamask.
2. **Deploy**: Escolha o contrato compilado e clique em "deploy". Isso enviará o contrato para a blockchain, e você terá que confirmar a transação na Metamask.

### Exemplo Prático
Vamos criar um token chamado "CopilotToken" com o símbolo "CPT" e uma oferta total de 1 milhão de unidades.

```solidity
pragma solidity ^0.8.0;

contract CopilotToken {
    string public name = "CopilotToken";
    string public symbol = "CPT";
    uint256 public totalSupply = 1000000;

    constructor() {
        balanceOf[msg.sender] = totalSupply;
    }

    mapping(address => uint256) public balanceOf;

    function transfer(address _to, uint256 _value) public returns (bool success) {
        require(balanceOf[msg.sender] >= _value);
        balanceOf[msg.sender] -= _value;
        balanceOf[_to] += _value;
        return true;
    }
}
```

Este é um exemplo básico de um contrato ERC-20, que é um padrão para a criação de tokens na Ethereum blockchain. Lembre-se de que, na prática, você precisará implementar funções adicionais e considerações de segurança.

Espero que isso ajude a quem precisa começar seu projeto de token.
