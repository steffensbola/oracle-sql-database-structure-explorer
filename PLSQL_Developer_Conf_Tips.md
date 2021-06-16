# PL/SQL Developer Productivity Tips  
  
PL/SQL Developer by Allround Automations is an IDE that is specifically targeted at the development of stored program units for Oracle Databases.  


## Auto Replace
Go to **Preferences** –> **Editor** –> **AutoReplace (auto-replace)** –> **Edit**
Add the following, one shortcut per line:
```
S=SELECT * FROM e_nome_entidade WHERE column_name = ;
I=INSERT INTO e_nome_entidade values ( , , );
U=UPDATE e_nome_entidade set column_name =  WHERE column_name = ;
F=FROM
W=WHERE
O=ORDER BY
D=DELETE
DF=DELETE FROM
SF=SELECT * FROM
SC=SELECT COUNT (*) FROM e_nome_entidade;
SFU=SELECT * FROM FOR UPDATE
COR=CREATE OR REPLACE
P=PROCEDURE
FN=FUNCTION
T=TRIGGER
V=VIEW
SSO=SET serveroutput on;
CT=CREATE TABLE e_nome_entidade (cd_chave_primaria  NUMBER NOT NULL, cd_chave_estrangeira NUMBER, dtultalteracao  TIMESTAMP(6));
CPK=ALTER TABLE e_nome_entidade  ADD CONSTRAINT pke_nome_entidade PRIMARY KEY (cd_chave_primaria);
CFK=ALTER TABLE e_nome_entidade  ADD CONSTRAINT fke_nome_entidade_nome_associada FOREIGN KEY (cd_chave_estrangeira) REFERENCES E_NOME_TABELA_RELACIONADA (cd_chave_estrangeira);
CS=CREATE SEQUENCE s_nome_entidade;
GS=GRANT SELECT ON schema_name.sequence_name_or_table TO user_or_role_name;
GA=GRANT ALL PRIVILEGES on schema_name.sequence_name_or_table to user_or_role_name;

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
