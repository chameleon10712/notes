Database Design
=================

Database System Concept

Chapter 7 ~ 9

|

Ch 7 Database Design and the E-R Model
========================================

E-R Model

- entity- relationship data model (E-R)

|

7.1 Overview of the Design Process
------------------------------------


- design of the database schema
- design of the programs that access and update the data
- design of a security scheme to control access to data

|

Design Phases
++++++++++++++

1. 了解使用者需求，並製作 user requirement spec
2. 選擇 data model 

- 最後會產生一個 entity-relationship diagram (provides a graphic representation of the schema)
- 屬於 conceptual-design phase
|

3. 以 specification of functional requirements 來描述 user 可能的 DB 操作
4. 根據上階段的 schema 實作

- logical-design phase => physical-design phase



Design Alternatives
+++++++++++++++++++++

在設計時需要避免兩大陷阱(pitfalls)

1. Redundancy
2. Incompleteness (ex. workaround)

|

7.2 The Entity-Relationship Model
===================================

ER Model 使用了三個基本概念:

- entity sets
- relationship sets
- attributes

