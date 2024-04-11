## Pytorch model tutorial with Iris data
Khyatee Desai

1. import numpy, pandas, torch, and DataLoader, Dataset from torch.utils.data
2. read 'iris.csv' into pandas and convert everything except last column into numpy array, named X. Shape should be (150, 4)

3. Create class Model with param torch.nn.Module
4. def __init__(self) should include 3 linear layers using torch.nn.Linear(4, ) followed by a sigmoid using torch.nn.Sigmoid()

5. def forward(self, x) with three sigmoid activation functions which take each of the linear layers as inputs, return the last activation

6. create Dataset class with param Dataset
7. def __init__(self) which contains the pd read csv from step 1, self.len which is the length of the df, self.x_data, and self.y_data which are the features and target column
- def __len__(self) which returns the length of the 
- def __getitem__(self, index) which returns x_data and y_data at a given index

8. instantiate a model and dataset object by calling the classes

9. create a torch dataloader and include the params of my dataset, batch_size=16, shuffle=True, num_workers=0

10. define the loss function as cross entropy loss
11. define the optimizer as SGD, include the model's parameters and a learning rate of 0.05 as params

11. write the training loop which iterates over 3 epochs, then iterates over the enumerated dataloader object:
- define the inputs and labels tuple from the dataloader
- do a forward pass to get preds
- get and print the loss
- zero the gradients
- back propogation
- take a step with the optimizer

