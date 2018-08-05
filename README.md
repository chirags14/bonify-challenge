# bonify-challenge

##Question 1 (Level 1) (10 min)
Assume a blacklist IP monitoring system, where any user trying to access the system,
is checked against a blacklist of IPs, and the connection is dropped if the IP was
found to be blacklisted.
Given a list of IPs (independent of size, can be anywhere from 1 record, to 50,000,000
records and more), design a database / cache structure to store those IPs for fast
lookup, based on an incoming users IP.
Expected result: data model, format of the keys/values, description of the reasoning
of your choices.

###Solution: 

An efficient way of doing this is binary search, given that all these IP ranges don't overlap
Steps to implement solution would be in below steps.
1.	Convert the range A.B.C.D/X into a 32-bit integer representing the starting IP address, as well as an integer of how many IPs in this range. For example, 192.168.1.0/24 converts to 3232235776, 256.
2.	Add these ranges in a list or array, and sort by the starting IP address number.
3.	To match an incoming IP address to any range in the list is to do the binary search.

=================================================================================================================

##Question 2 (Level 1) (20 min)
Assume a database of categories, and keywords associated with a category, with an
N-to-N relation between them. You need to analyze a file attachment (such
as .pdf, .doc, .xml), and find the most fitting category for this file, based on the file's
contents, and number of keyword occurrences per category.
Categories & Keywords for example:
Category: Computers; Keywords: Networking, Keyboard, Mouse, Processor, RAM
Category: Clothing; Keywords: Pants, Shoes, T-Shirt, Dress Shirt, Socks

###Solution:

Approach to solve this problem would be in below steps.
1.	Read the file in given document format.
2.	Use HashMap to store categories as key and value as number of keyword occurrence.
For example, while iterating file content check each sentence against given category and if category is matched based on keyword, increment the counter in HashMap for that category. At they end of iteration you will have HashMap with maximum number of occurrences for given category.

=================================================================================================================

##Question 3 (Level 2) (1 hour)
You have following code part below which consist of several “if else” statements. You
need to optimize the code to support different data types in the future without
changing it one more time.
public void processContract(String type) {
if ("electricity".equals(type)) {
System.out.println("Processed electricity");
} else if ("dsl".equals(type)) {
System.out.println("Processed dsl");
} else if ("appartment_rent".equals(type)) {
System.out.println("Processed appartment");
}
}
Expected result: java Spring Boot application that can receive a “type”(dsl or other) as
an input and prints to console what was selected. Step by step explanation of how to
run the project.

###Solution:
Please refer below GitHub Repo for my solution

https://github.com/chirags14/bonify-type-identifier.git

=================================================================================================================

##Question 5 (Level 3) (2 hours)
Given the following content of a csv file:
name;bank_identifier
Postbank;10010010
Eurocity;10030700
Commerzbank;10040000
Raiffeisenbank;22163114
1. Write a program which imports the entries of the csv file into a database of your
choice (preferably PostgreSQL)
2. Fetch the record with the bank identifier 10040000 from DB and print the name
of the related bank to system out.

###Solution:
Please refer below GitHub Repo for my solution

https://github.com/chirags14/bonify-bank-management-service.git
