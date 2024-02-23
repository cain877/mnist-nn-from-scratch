## MNIST NN with two hidden layers (No TensorFlow)
### author: @zanolablue

Simple MNIST NN inspired by Samson Zhang video with updated normalization and an added hidden layer using the ReLU activation function, improving accuracy.
Below are the equations for the propagations:

**Forward propagation**

* 𝑍[1]=𝑊[1]𝑋+𝑏[1]
  
* 𝐴[1]=𝑔ReLU(𝑍[1]))
  
* 𝑍[2]=𝑊[2]𝐴[1]+𝑏[2]
 
* 𝐴[2]=𝑔ReLU(𝑍[2]))
 
* 𝑍[3]=𝑊[3]𝐴[2]+𝑏[3]
 
* 𝐴[3]=𝑔softmax(𝑍[3])
  
**Backward propagation**

* 𝑑𝑍[3]=𝐴[3]−𝑌
  
* 𝑑𝑊[3]=1𝑚𝑑𝑍[3]𝐴[2]𝑇
  
* 𝑑𝐵[3]=1𝑚Σ𝑑𝑍[3]
 
* 𝑑𝑍[2]=𝑊[3]𝑇𝑑𝑍[3].∗𝑔[1]′(𝑧[2])
  
* 𝑑𝑊[2]=1𝑚𝑑𝑍[2]𝐴[1]𝑇
  
* 𝑑𝐵[2]=1𝑚Σ𝑑𝑍[2]
  
* 𝑑𝑍[1]=𝑊[2]𝑇𝑑𝑍[2].∗𝑔[1]′(𝑧[1])
  
* 𝑑𝑊[1]=1𝑚𝑑𝑍[1]𝐴[0]𝑇
  
* 𝑑𝐵[1]=1𝑚Σ𝑑𝑍[1]
 
**Parameter updates**

* 𝑊[3]:=𝑊[3]−𝛼𝑑𝑊[3]

* 𝑏[3]:=𝑏[3]−𝛼𝑑𝑏[3]
 
* 𝑊[2]:=𝑊[2]−𝛼𝑑𝑊[2]
 
* 𝑏[2]:=𝑏[2]−𝛼𝑑𝑏[2]
  
* 𝑊[1]:=𝑊[1]−𝛼𝑑𝑊[1]
  
* 𝑏[1]:=𝑏[1]−𝛼𝑑𝑏[1]

Where the activation function ReLU() is being used for the hidden layers and softmax() is used to activate the output layer denoted by A[3]
