# Lab_1NathanBabchuk

> Nathan_Babchuk

----

> ***Consignment Agreement***


## Consignment Agreement View

### 0NF - Meta Data

**Consigment Agreement** <span class="md"><b class="pk">Consignment ID</b>, Customer ID, Customer Firstname, Customer Lastname, Customer Type ID, Customer Type Description, Date, <b class="rg">Line#, Description, Start Price, Low Price, Category Code, Category Description, Category Cost,</b>, Subtotal, Rewards Discount, GST, Total</span>

### 1NF - Repeating Groups

**Consignment View** <span class="md"><b class="pk">Consignment ID</b>, Customer ID, Customer Firstname, Customer Lastname, Customer Type ID, Customer Type Description, Date, Subtotal, Rewards Discount, GST, Total</span>

**Consignment Detail** <span class="md"><b class="pk"><u class="fk">Consignment ID</u>, Line#</b>, Description, Start Price, Low Price, Category Code, Category Description, Category Cost,

### 2NF - Partial Depenencies

**Consignment View** <span class="md"><b class="pk"><u class="fk">Consingment ID</u>, <u class="fk">, Line#</u></b>, Description, Low Price, Category Description,</span>

**Consignment Item**  <span class="md"><b class="pk">Line#</b>, Start Price, Categroy Code, Category Cost,

### 3NF - Transitive Dependencies 

**Consignment View** <span class="md"><b class="pk">Consingment ID</b>, <u class="fk">Customer ID</u>, Subtotal, Rewards Discount, GST, Total</span>

**Customer Consignment View** <span class="md"><b class="pk">Customer ID, Customer Firstname, Customer Lastname, Date,</span>

<img src="database/data123.png">

***Staff Training***
### 0NF - Meta Data

**Staff Training** <span class="md"><b class="pk">Staff ID</b>, Staff Name, Type ID,
 Type Name,  <b class="rg"> Training ID, Description, Start Date, End Date, Pass/fail,</span>

 ### 1NF - Repeating Groups

**Staff Training View** <span class="md"><b class="pk">Staff ID</b>, Staff Firstname, Staff Lastname, Type ID, Type Name</span>

**Staff Training Detail**  <span class="md"><b class="pk"><u class="fk">Staff ID</u>, Training ID</b>, Description, Start Date, End Date, Pass/fail,</span>

### 2NF - Partial Depenencies

**Staff Training View** <span class="md"><b class="pk"><u class="fk">Staff ID</u>, <u class="fk">, Training ID</u></b>, Description, End Date

**Staff Training View** <span class="md"><b class="pk">Training ID</b>, Start Date, Pass/fail,</span>

### 3NF - Transitive Dependencies 

**Staff Training Start** <span class="md"><b class="pk">Staff ID</b>, <u class="fk">Training ID</u>, Description, Start Date, End Date, Pass/fail,</span

>**Staff Training Results** <span class="md"><b class="pk">Training ID, Staff First name, Staff Last name, Type ID, Type Name, </span> 

***Customer Rewards***

### 0NF - Meta Data

**Customer Rewards** <span class="md"><b class="pk">Customer ID</b> First name, Last name, Address, Email, Phone, Reward code,<b class="rg">, Rewarded Description, Discount Percentage,

### 1NF - Repeating Groups

**Customer rewards View** <span class="md"><b class="pk">Customer ID</b>, First name, Last name, Address, Email, Phone,</span>

**Customer rewards Detail** <span class="md"><b class="pk"><u class="fk">Customer ID</u>, Rewardcode</b>, Reward Description, Discount Percentage,</span>

### 2NF - Partial Dependencies
**This Data Has No partial dependencies**

### 3NF - Transitive Dependencies 

**Customer Rewards View** <span class="md"><b class="pk">Customer ID</b>, <u class="fk">Reward Code</u>, First name, Last name, Address, Email, Phone,</spam></b>

**Customer rewards result** <span class="md"><b class="pk">Reward code, Reward Description, Discount Perecentage,</span>






<style>
.md {
    display: inline-block;
    vertical-align: top;
    white-space:normal;
}
.md::before {
    content: '(';
    font-size: 1.25em;
    font-weight: bold;
}
.md::after {
    content: ')';
    font-size: 1.25em;
    font-weight: bold;
}
.pk {
    font-weight: 700;
    display: inline-block;
    border: thin solid #00f;
    padding: 0 2px;
    position: relative;
}
.pk::before {
    content: 'P';
    font-size:.55em;
    font-weight: bold;
    color: white;
    background-color: #72c4f7;
    position: absolute;
    left: -5px;
    top: -15px;
    border-radius: 50%;
    border: solid thin blue;
    width: 1.4em;
    height: 1.4em;
    padding:3px;
    text-align:center;
}
.fk {
    color: green;
    font-style: italic;
    text-decoration: wavy underline green;
    padding: 0 2px;
    position: relative;
}
.fk::before {
    content: 'F';
    font-size:.65em;
    position: absolute;
    left: -1px;
    bottom: -17px;
    color:darkgreen;
    background-color: #a7dea7;
    border-radius: 50%;
    border: dashed thin green;
    width: 1.4em;
    height: 1.4em;
    padding:3px;
    text-align:center;
}
.rg::before {
    content: '\007B';
    color: darkorange;
    font-size: 1.2em;
    font-weight: bold;
}
.rg::after {
    content: '\007D';
    color: darkorange;
    font-size: 1.2em;
    font-weight: bold;
}
.rg {
    display: inline-block;
    color: inherit;
    font-size: 1em;
    font-weight: normal;
}
.note {
    font-weight: bold;
    color: brown;
    font-size: 1.1em;
}
</style>

----

## Legend

This legend is a guide to reading and interpreting the table listings under 0NF through 3NF.

- **TableName:**
  - Table names will be bolded and end with a colon. (e.g.: `**TableName:**`)
- (Column, Names)
  - Column names for a table will be enclosed in (rounded parenthesis) (e.g.: `<span class="md">All, Attributes</span>`).
- <b class="pk">PrimaryKeyFields</b>
  - Primary key fields will be bold and inside a box. (e.g.: `<b class="pk">PrimaryKeyFields</b>`)
- <u class="fk">ForeignKeyFields</u>
  - Foreign key fields will be a wavy underline in italic and green. (e.g.: `<u class="fk">ForeignKeyFields</u>`)
- <b class="rg">Repeating Groups</b>
  - Groups of repeating fields will be identified in 0NF stage, and will be enclosed in orange curly braces. (e.g.: `<b class="rg">Repeating, Group, Fields</b>`)
