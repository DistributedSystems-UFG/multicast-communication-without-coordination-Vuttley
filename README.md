Aluno: Matheus Carlos Lima e Silva <br>
Matrícula: 202004728 <br> <br> <br>

## <b>Funcionamento básico</b> <br> <br>

&emsp; Nesse sistema cada processo envia mensagens de "handshake" para indicar prontidão e, em seguida, troca mensagens de dados. As mensagens são armazenadas em arquivos de log individuais e comparadas por um servidor central. <br> <br>

## <b>Componentes</b> <br> <br>

### Handshake e Inicialização <br> <br>

&emsp; Cada processo peer inicia enviando mensagens de "handshake" para indicar que está pronto para se comunicar. <br>
&emsp; Os handshakes são trocados entre os peers para estabelecer a disponibilidade de todos. A recepção de mensagens só começa após todos os processos enviarem seus hadshakes (handShakeCount = N). <br> <br>

### Recepção de Dados <br> <br>

&emsp; Cada processo peer cria uma thread chamada MsgHandler para lidar com a recepção de mensagens de dados dos outros peers. <br>
&emsp; As mensagens são recebidas usando um socket e são armazenadas em arquivos de log individuais para cada peer. <br> <br>

### Comparação de Mensagens <br> <br>

&emsp; Após receber todas as mensagens de dados, os peers enviam suas mensagens para um servidor de comparação usando um socket. <br>
&emsp; O servidor compara as mensagens de todos os peers para verificar se as ordens são consistentes. <br> <br>

### Encerramento da Comunicação <br> <br>

&emsp; Os peers enviam mensagens de "stop" quando não têm mais mensagens para enviar. <br>
&emsp; Quando todos os peers enviaram suas mensagens de "stop", a comunicação é encerrada.



