<h1>Neural Network</h1>

<p>Welcome to the Neural Network repository! This project focuses on developing a parallelized neural network implementation that takes advantage of multi-core processing. The proposed operating system utilizes parallel computation to enhance the overall processing power of the system.</p>

<h2>Approach</h2>

<p>In a multi-core processor, the system utilizes several processing units (cores) capable of executing multiple threads simultaneously. To leverage this capability, the neural network implementation follows the following approach:</p>

<ul>
  <li>Each layer of the neural network is represented as a separate process.</li>
  <li>Each neuron within a layer is treated as a separate thread.</li>
  <li>Threads are assigned to different cores of the processor for parallel processing of inputs.</li>
</ul>

<h2>Inter-Process Communication</h2>

<p>The operating system provides a mechanism for inter-process communication (IPC) through pipes. These pipes facilitate the exchange of information between processes. In the context of the neural network, weights and biases, which are the parameters learned during training, are exchanged through these pipes.</p>

<h2>Training Approach</h2>

<p>During training, the system adopts a batch-based approach, where the input data is divided into smaller batches. Each batch is then processed by a separate layer in the neural network. The processing flow is as follows:</p>

<ol>
  <li>Each layer receives its input batch from the previous layer through a pipe.</li>
  <li>The layer applies the weights and biases to the input batch to generate the output.</li>
  <li>The output is passed to the next layer as input through another pipe.</li>
</ol>

<h2>Utilizing Multiple Cores</h2>

<p>The system effectively utilizes multiple cores by distributing the computation across them. This parallelization enables faster processing of large datasets. Locking mechanisms are implemented to prevent multiple threads from accessing the same resource simultaneously, ensuring data integrity.</p>

<h2>Backpropagation</h2>

<p>During backpropagation, the error signal propagates backward through the layers of the neural network. The system updates the weights and biases based on the calculated gradients. To utilize the processing power of multiple cores during backpropagation, the system divides the computation into smaller tasks and assigns each task to a different core.</p>

<h2>Backpropagation</h2>

<p>During backpropagation, the error signal propagates backward through the layers of the neural network. The system updates the weights and biases based on the calculated gradients. To utilize the processing power of multiple cores during backpropagation, the system divides the computation into smaller tasks and assigns each task to a different core.</p>

<h2>Compile and Run</h2>

<p>To compile and run the code on Linux using the pthread library, follow these steps:</p>

<ol>
  <li>Clone this repository to your desired location using the following command:</li>
</ol>

<pre><code>git clone https://github.com/your-username/your-repository.git</code></pre>

<ol start="2">
  <li>Navigate to the project directory:</li>
</ol>

<pre><code>cd your-repository</code></pre>

<ol start="3">
  <li>Compile the code using the following command:</li>
</ol>

<pre><code>g++ -o neural_network -pthread proj.cpp</code></pre>

<ol start="4">
  <li>Run the compiled code:</li>
</ol>

<pre><code>./neural_network</code></pre>

<p>Make sure to configure any necessary dependencies and ensure compatibility with your system.</p>


