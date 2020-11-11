# LendingClubLoan_Project
# Overview

LendingClub is a peer-to-peer lending company from USA headquartered in San Francisco, California. This company provides the first peer-to-peer loan with security services as a selling point, namely the Securities and Exchange Commission (SEC), in addition the company also offers trading loans on the secondary market. LendingClub is the world's largest peer-to-peer lending platform.

The purpose of this data analysis is to predict whether a prospective customer will pay off his loan

# Code Resources

Python Version: 3

Packages: pandas, numpy, sklearn, matplotlib, seaborn, keras.

dataset = https://www.kaggle.com/wordsforthewise/lending-club

# Data Cleaning

After I got the dataset, data cleaning was performed on the data so that it could be used for modeling.
* eliminates _employer title_ and _employer length_.
* Mixing _title_ with _purpose_ because it has same output.
* fill in the missing data in _mort_acc_ with the average value of _mort_acc_ by _total_acc_.

# EDA

Here are some examples of data analysis results

>![Melihat Data kemampuan nasabah melunasi pinjaman](/loan_status.png)

Graph 1 shows how many customers can pay off their loans and who cannot

>![Data berdasarkan Grade](/grade.png)

Graph 2 shows the customer's ability to pay off their loan based on the _grade_ of the customer.

# Model Building

First, I changed the categorical variables into dummy variables, then converse 20% of the total data into training data.

With the _deep learning_ method, I used _Neural Network_ with an _input layer_ of 78 cells. _Hidden layer_ that I use is the previous cell divided by 2 with the _ReLU_ (_Rectified Linear Unit_) activation method. Meanwhile, the _output layer_ uses the method of sigmoid activation, optimization of _adam_ and loss of _binary-crossentropy_. All of methods used in this case is chosed because there are only 2 outputs, Yes (_Full Paid_) or No (_Charged Off_).
![Model](/model.png)

From the graph, we can see the relationship between training results (loss) and data validation (validation). With this model I will try to predict random data.

# Model Performance

After being tested by random data using this model, I'm sure 89% can predict whether a prospective customer can pay off his loan.
