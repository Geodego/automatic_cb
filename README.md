# Automatic pricing and strategy learning on convertible bonds
Project developed at Exane. This is a description of the project, the project repository is private.


## Project Description
### Purpose:
* Automatically manage all the processes taken by a Convertible Bonds trader when making prices and when taking trading 
decisions. By rationalizing these different steps, the performance of a portfolio can be made more 
robust over time. Moreover, the number of trading decisions, the scope of action and the set of strategies explored 
by the trader can be extended dramatically. 
* Build quality data that can be used to learn trading strategies.

To achieve these targets two main tasks were put in place:
* Building a Python framework that centralizes all sources of information and handle all potential actions to be taken 
in one place.
* Building a SQL database where relevant data can be saved in an organised fashion. 
This data allows performing analysis based on information not necessarily available in the
market.

### Actions than can be performed using this program:
The framework can perform the following tasks on the fly:

* Calculate our market making prices and update our pricing contributions to Bloomberg and to clients. 
To perform that task, the system uses as inputs: market prices (Quanthouse, Bloomberg, IDB prices), axes from the book 
and interests from clients. 
* Update Convertible Bonds prices. The system can automatically adjust Convertible Bonds pricing parameters, 
deciding which part of the adjustment should come from the credit spread and which part should come from the volatility. 
This allows to calculate the mark to market of the book and to remark it automatically. This also allows to update 
prices on all the universe followed and to build detailed data on valuation variations (impact from contribution 
margins, from rates, from volatility and from credit).
* Compute theoretical volatility levels. Uses volatility surfaces as computed by the option trading desk and historical 
volatility to compute theoretical volatility parameters for Convertible Bonds.
* Compute theoretical credit levels. Use credit information from the market 
(Itraxx Xover, CDS and straight credit prices) to compute theoretical credit parameters for Convertible Bonds.


### Organisations of the different tasks that were put in place for building this project:
To build that project I had to work with several members of different IT teams (market data, pricing distribution and 
central database). They developed the different APIs needed for the project while I was left with developing the Python 
side of the project and the dedicated database.
Here is a list of the main tasks performed: 
* Building an API to connect to Quanthouse (market data team)
* Building an API to connect to one of our IDB (market data team)
* Adapting the in-house pricing API so that we could access it from our Python framework (pricing distribution team)
* Building APIs to access different in-house databases and the contribution systems (central database/market data teams).
* Building an SQL database dedicated to the project.
* Using the Bloomberg API to build objects for our purpose.
* Developing the Python framework centralizing all these APIs and executing relevant actions.

### Tests
Tests are performed using pytest.


