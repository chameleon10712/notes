Database Design
=================

Database System Concept

Chapter 7 ~ 9

|

Ch 7 Database Design and the E-R Model
========================================

- E-R Model

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

- 在設計時需要避免兩大陷阱(pitfalls)

  1. Redundancy
  2. Incompleteness (ex. workaround)

|

7.2 The Entity-Relationship Model
===================================

ER Model 使用了三個基本概念:

- entity sets
- relationship sets
- attributes


Entity Sets
-------------
- entity 

  - ex. person_id
  
- entity set  

  - ex. 由多個 person_id 組成的 instructor

- attributes

  - 多個 attributes 組成一個 entity
  - 每個 attribute 都有一個 value




Relationship Sets
-------------------

- relationship

  - 描述 entity 之間的關係

- relationship sets

  - 一組 relationships

- role

  - The function that an entity plays in a relationship is called that entity’s role.

- recursive relationship set

  - when the entity sets of a relationship set are not distinct; that is, the same entity set participates in a relationship set more than once, in different roles. 
  - 需要 explicit role names 來描述關係


- descriptive attributes

  - 有些時候 relationship 也會用 descriptive attributes 來描述關係


Attributes
------------

- domain
- value set


Attribute Types
+++++++++++++++++

- Simple and composite attributes

  - composite attributes
    
    - name 這個 attribute 可以再細分為 first name, middle name, last name
    - address 這個 attribute 可以再細分為 street, city, state, zip code

- Single-valued and multi-valued attributes

  - single valued
  
    - 一個 student_id 只會對應到一個學生
  
  - multi valued
  
    - 一個學生可能有好幾支電話

- Derived attribute

  - 一個具有 students_advices attribute 的 instructor ，根據 relationship 可以查出他 advice 的學生名單

