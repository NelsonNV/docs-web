# BOOMCAPMS base de datos


## Paginas WEB

- **HOSTING** = servicio de alojamiento

un hosting permite tener correos, manipular archivos, crear y connectar a bases de datos.

- **DOMINIO** = una dirrecion de ip validad que apunta a un hosting

podemos decir que un dominio es una direcion ip tranformadas en un formato leibre para una persona y facil de ubicar
**ejemplo** 

- navarrolabs = 190.107.177.250

los hosting tiene por lo general un panel de  configuracion usual mente llamado **CPANEL**

tambien puedes subdividir un DOMINIO el cual siempre se pondra antes del dominio principal
por ejemplo algo asi 

- api.navarrolabs

en este caso el sub dominio seria **api** y el dominio **navarrolabs**

Como dato extra un **host** significa alfitrion.

## TIPOS DE RETRICCIONES EN UNA TABLA

hay distintos tipos de retricciones que permiten definir reglas o condiciones en una tabla

1. **PRIMARY KEY - PK**: valores dupricados, no puede tener valores nulos
2. **FORANI KEY - FK**: Solo se pueden usar valores correctos.
3. **UNIQUE KEY - UK**: no acepta valores duplicados
4. **NOT NULL**: no puede tener valores nulos
5. **CHEK**:  es como un IF, ayuda a definir reglas de negocio

algunos ya los abras visto al crear una tabla como el not null que es muy utilizado
pero por ejemplo un chek permite crear reglas de negocio como que un sueldo no pueda ser inferior a un numero.

### NDS native dynamic sql

es usar sql de forma dinamica e nque el que suas procedimiento que recive parametros

por ejemplo una funcion que te permite eliminar una tabla en la que te pide como parametro el nombre de la tabla
de esta forma puedes ahorrar algunos trabajos como tambien evitar posible injecciones de datos. ya que no sabes como es el codigo
pero si sabes cual es la funcion.

### NOMBRES PARA UN ADMIN

por lo general un admin adquiere los siguientes nombres

**ADMIN** = **SYSTEM** = **SYS** = **SYSBDA** = **DBA** = **OWNER**


1 usario = 1BD = 1 TABLESPACE

ROL es un conjunto de privilegios

### roles general mente usado
- **CONNECT** = crear sesiones, conectarse a usuarios , comunicacion
- **RESOURCE** = acceder al espacio fisico, a las tablas y otros objetos


## CREAR USUARIOS
````sql
--crear usuario
CREATE USER NNAVARRO IDENTIFIED BY "12345"
DEFAULT TABLESPACE SYSAUX
TEMPORARY TABLESPACE TEMP;
-- definir limite de trabajo
ALTER USER NNAVARRO QUOTA UNLIMITED ON SYSAUX;
-- privilegios
GRANT CREATE SESSION TO NNAVARRO;
GRANT RESOURCE TO NNAVARRO;

````
### CREAR TABLAS
``` sql
CREATE TABLE tbl_usuario(
    id_usuario NUMBER NOT NULL,
    rut NUMBER(8) NOT NULL UNIQUE,
    dv VARCHAR2(1) NOT NULL,
    nombre VARCHAR2(20) NOT NULL,
    apellido VARCHAR2(20) NOT NULL,
    PRIMARY KEY (id_usuario)
);
```
### CREAR SECUENCIAS
```sql
CREATE SEQUENCE seq_usuario START WITH 100
INCREMENT BY 10;
```
### INSERCION DE DATOS CON SECUENCIAS
```sql
INSERT INTO tbl_usuario VALUES(SEQ_USUARIO.nextval,20114257,'0','Alan','Brito');
```
- **nextval**: siguiente valor
- **currval**: actual valor

## USO DE TABLA DUAL
la tabla dual sirve para hacer muchos ejercicios y pruebas es una tabla que contiene un solo dato pero es lo mejor para experimentar
```sql
SELECT
    SEQ_USUARIO.CURRVAL 
FROM
    dual;
```	
## SEGURIDAD
### CONCEDER PRIVILEGIOS DE OBJETOS
``` sql
GRANT SELECT ON IBILBAO.TBL_COMUNA TO NNAVARRO;
GRANT DELETE ON IBILBAO.TBL_USUARIO TO NNAVARRO;
GRANT UPDATE ON IBILBAO.TBL_USUARIO TO NNAVARRO;
```
### CONCEDER PRIVILEGIOS DE SISTEMA
```sql
GRANT CREATE SESSION TO "IBILBAO";
GRANT CREATE ANY TABLE TO NNAVARRO;

```
### CONCEDER ROLES
```sql
GRANT CONNECT TO NNAVARRO;
```

### REVOCAR PRIVILEGIOS DE OBJETOS
```sql
REVOKE SELECT ON IBILBAO.TBL_USUARIO FROM NNAVARRO;
```
### REVOCAR PRIVILEGIOS DE SISTEMA
```sql
REVOKE CREATE ANY TABLE FROM NNAVARRO;
```

