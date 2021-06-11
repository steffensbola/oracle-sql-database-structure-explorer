# PL/SQL Developer Productivity Tips  
  
PL/SQL Developer by Allround Automations is an IDE that is specifically targeted at the development of stored program units for Oracle Databases.  


## Auto Replace
Go to **Preferences** –> **Editor** –> **AutoReplace (auto-replace)** –> **Edit**
Add the following, one shortcut per line:
```
S=SELECT * FROM TABLE_NAME WHERE FIELD_NAME = ;
I=INSERT INTO TABLE_NAME values ( , , );
U=UPDATE TABLE_NAME set FIELD_NAME =  WHERE FIELD_NAME = ;
F=FROM
W=WHERE
O=ORDER BY
D=DELETE
DF=DELETE FROM
SF=select * FROM
SC=SELECT COUNT (*) from TABLE_NAME;
SFU=SELECT * FROM FOR UPDATE
COR=CREATE OR REPLACE
P=PROCEDURE
FN=FUNCTION
T=TRIGGER
V=VIEW
SSO=SET serveroutput on;
CT=CREATE TABLE E_NOME_ENTIDADE (CD_CHAVE_PRIMARIA  NUMBER NOT NULL, CD_CHAVE_ESTRANGEIRA NUMBER, DTULTALTERACAO  TIMESTAMP(6));
CPK=ALTER TABLE E_NOME_ENTIDADE  ADD CONSTRAINT PKE_NOME_ENTIDADE PRIMARY KEY (CD_CHAVE_PRIMARIA);
CFK=ALTER TABLE E_NOME_ENTIDADE  ADD CONSTRAINT FKE_NOME_ENTIDADE_E_NOME_ASSOCIADA FOREIGN KEY (CD_CHAVE_ESTRANGEIRA) REFERENCES E_NOME_TABELA_RELACIONADA (CD_CHAVE_ESTRANGEIRA);
CS=CREATE SEQUENCE S_NOME_ENTIDADE;

```

##  Automatic Capitalization  
  
When you enter SQL statements in a window, the keywords are automatically capitalized, and the others are lowercase.  
This is easy to read code, and to maintain a good coding style.  
  
Go to **Preferences** –> **Editor** –> **Keyword case**  
Select `uppercase`.  
  

## Hint Delay Time  
  
Go to Preferences->Code Assistant (assistant) and set **Automatically Activated** to `true` and the code hint **Delay** to `300` ms or so.    
Now, when you are using the editor, enter a few characters and the tool will suggest the database objects.  
  
## Toogle Comment  
  
Go to **Preferences** –> **User Interface** –> **Key configuration**.  
Find **Edit / Selection / Comment** and set the key combination you want to use.  

## Connect faster with saved passwords  
  
Go to **Preferences** –> **Oracle** –> **Logon History**.  
Set **Store History** and **Store with password** to `true`.  
In the **Fixed Users** field insert your connections, one for each line, in the following format:  
```
user1/password1@database1
user2/password2@database2
```  

## Commit  
  
By default DML statements (INSERT/DELETE/UPDATE/MERGE) don't do an auto commit in PL/SQL.  
DDL statements do commit (ALTER/CREATE etc) and this will happen even if something failed.  

To change the autocommit behavior for DML statements to **Preferences** –> **Window Types** –> **SQL Window**.  
Set **AutoCommit SQL** to `true`. 

## Show line numbers  
  
Go to **Preferences** –> **Window Types** –> **SQL Window**.   
Set **Show Gutter** to `true`.  


# Note
These tips where inspired by a blog post from [Alibaba Cloud](https://topic.alibabacloud.com/a/plsql-developer-usage-tips-shortcut-keys_8_8_30066914.html).  
