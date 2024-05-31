## Documentação Simplificada do Modelo Relacional

*Projeto:* Borbulha

*Data:* 2024-05-09

*Autor:* Isabelle Messias Dantas Pereira

*Objetivo:* A Modelagem de Dados é uma etapa imprescindível para a esquematização de modelos de bancos de dados. Nesse contexto, saber estruturá-los para uma análise adequada das informações é muito importante para garantir a qualidade e a eficiência do sistema.

## Entidades

- *Usuários* (users): Armazena informações básicas sobre os usuários (nome, email, senha e estado).
- *Feed e comunidade* (feed_and_comunity): Armazena os detalhes das postagens feitas no feed ( id do usuário, data de criação, id do tipo de publicação e título, descrição, duração e quantidade de voluntários para o projeto)


## Relacionamentos

- A relação de users e feed_and_comunity é de 1:N 

## Regras de Negócio

- Todos os campos obrigatórios devem ser preenchidos.
- As informações devem ser consistentes entre os formulários.
- Os usuários não podem editar informações já salvas, exceto em casos específicos.
- As informações dos usuários são confidenciais.

## Arquivo em xml

```xml 
<?xml version="1.0" encoding="utf-8" ?>
<!-- SQL XML created by WWW SQL Designer, https://github.com/ondras/wwwsqldesigner/ -->
<!-- Active URL: https://sql.toad.cz/ -->
<sql>
<datatypes db="mysql">
	<group label="Numeric" color="rgb(238,238,170)">
		<type label="Integer" length="0" sql="INTEGER" quote=""/>
	 	<type label="TINYINT" length="0" sql="TINYINT" quote=""/>
	 	<type label="SMALLINT" length="0" sql="SMALLINT" quote=""/>
	 	<type label="MEDIUMINT" length="0" sql="MEDIUMINT" quote=""/>
	 	<type label="INT" length="0" sql="INT" quote=""/>
		<type label="BIGINT" length="0" sql="BIGINT" quote=""/>
		<type label="Decimal" length="1" sql="DECIMAL" re="DEC" quote=""/>
		<type label="Single precision" length="0" sql="FLOAT" quote=""/>
		<type label="Double precision" length="0" sql="DOUBLE" re="DOUBLE" quote=""/>
	</group>
	<group label="Character" color="rgb(255,200,200)">
		<type label="Char" length="1" sql="CHAR" quote="'"/>
		<type label="Varchar" length="1" sql="VARCHAR" quote="'"/>
		<type label="Text" length="0" sql="MEDIUMTEXT" re="TEXT" quote="'"/>
		<type label="Binary" length="1" sql="BINARY" quote="'"/>
		<type label="Varbinary" length="1" sql="VARBINARY" quote="'"/>
		<type label="BLOB" length="0" sql="BLOB" re="BLOB" quote="'"/>
	</group>
	<group label="Date &amp; Time" color="rgb(200,255,200)">
		<type label="Date" length="0" sql="DATE" quote="'"/>
		<type label="Time" length="0" sql="TIME" quote="'"/>
		<type label="Datetime" length="0" sql="DATETIME" quote="'"/>
		<type label="Year" length="0" sql="YEAR" quote=""/>
		<type label="Timestamp" length="0" sql="TIMESTAMP" quote="'"/>
	</group>
	
	<group label="Miscellaneous" color="rgb(200,200,255)">
		<type label="ENUM" length="1" sql="ENUM" quote=""/>
		<type label="SET" length="1" sql="SET" quote=""/>
		<type label="Bit" length="0" sql="bit" quote=""/>
	</group>
</datatypes><table x="599" y="122" name="users">
<row name="id" null="0" autoincrement="1">
<datatype>INTEGER</datatype>
</row>
<row name="name" null="0" autoincrement="0">
<datatype>VARCHAR(50)</datatype>
</row>
<row name="email" null="1" autoincrement="0">
<datatype>VARCHAR(50)</datatype>
<default>NULL</default></row>
<row name="password" null="1" autoincrement="0">
<datatype>VARCHAR(12)</datatype>
<default>NULL</default></row>
<row name="state" null="1" autoincrement="0">
<datatype>VARCHAR(50)</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="806" y="307" name="feed_and_comunity">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="id_users" null="0" autoincrement="0">
<datatype>INTEGER</datatype>
<relation table="users" row="id" />
</row>
<row name="created_at" null="1" autoincrement="0">
<datatype>DATETIME</datatype>
<default>NULL</default></row>
<row name="likes" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="id_type_posts" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="type_posts" row="id" />
</row>
<row name="project_title" null="1" autoincrement="0">
<datatype>VARCHAR(25)</datatype>
<default>NULL</default></row>
<row name="project_description" null="1" autoincrement="0">
<datatype>VARCHAR(250)</datatype>
<default>NULL</default></row>
<row name="project_duration" null="1" autoincrement="0">
<datatype>VARCHAR(50)</datatype>
<default>NULL</default></row>
<row name="project_volunteers_quantity" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="329" y="286" name="liked_contents">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="id_news_feed" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="feed_and_comunity" row="id" />
</row>
<row name="id_users" null="0" autoincrement="0">
<datatype>INTEGER</datatype>
<relation table="users" row="id" />
</row>
<row name="liked" null="1" autoincrement="0">
<datatype>BINARY</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="569" y="450" name="type_posts">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="type_post" null="1" autoincrement="0">
<datatype>VARCHAR(25)</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
</sql>

```
## Arquivo em sql

```sql
-- ---
-- Globals
-- ---

-- SET SQL_MODE="NO_AUTO_VALUE_ON_ZERO";
-- SET FOREIGN_KEY_CHECKS=0;

-- ---
-- Table 'users'
-- 
-- ---

DROP TABLE IF EXISTS `users`;
		
CREATE TABLE `users` (
  `id` INTEGER NOT NULL AUTO_INCREMENT,
  `name` VARCHAR(50) NOT NULL,
  `email` VARCHAR(50) NULL DEFAULT NULL,
  `password` VARCHAR(12) NULL DEFAULT NULL,
  `State` VARCHAR NULL DEFAULT NULL,
  PRIMARY KEY (`id`)
);

-- ---
-- Table 'feed_and_comunity'
-- 
-- ---

DROP TABLE IF EXISTS `feed_and_comunity`;
		
CREATE TABLE `feed_and_comunity` (
  `id` INTEGER NULL AUTO_INCREMENT DEFAULT NULL,
  `id_users` INTEGER NOT NULL,
  `created_at` DATETIME NULL DEFAULT NULL,
  `id_type_posts` INTEGER NULL DEFAULT NULL,
  `project_title` VARCHAR(25) NULL DEFAULT NULL,
  `project_description` VARCHAR(250) NULL DEFAULT NULL,
  `project_duration` VARCHAR(50) NULL DEFAULT NULL,
  `project_volunteers_quantity` INTEGER NULL DEFAULT NULL,
  PRIMARY KEY (`id`)
);

-- ---
-- Table 'liked_contents'
-- 
-- ---

DROP TABLE IF EXISTS `liked_contents`;
		
CREATE TABLE `liked_contents` (
  `id` INTEGER NULL AUTO_INCREMENT DEFAULT NULL,
  `id_news_feed` INTEGER NULL DEFAULT NULL,
  `id_users` INTEGER NOT NULL,
  PRIMARY KEY (`id`)
);

-- ---
-- Table 'type_posts'
-- 
-- ---

DROP TABLE IF EXISTS `type_posts`;
		
CREATE TABLE `type_posts` (
  `id` INTEGER NULL AUTO_INCREMENT DEFAULT NULL,
  `type_post` VARCHAR(25) NULL DEFAULT NULL,
  PRIMARY KEY (`id`)
);

-- ---
-- Foreign Keys 
-- ---

ALTER TABLE `feed_and_comunity` ADD FOREIGN KEY (id_users) REFERENCES `users` (`id`);
ALTER TABLE `feed_and_comunity` ADD FOREIGN KEY (id_type_posts) REFERENCES `type_posts` (`id`);
ALTER TABLE `liked_contents` ADD FOREIGN KEY (id_news_feed) REFERENCES `feed_and_comunity` (`id`);
ALTER TABLE `liked_contents` ADD FOREIGN KEY (id_users) REFERENCES `users` (`id`);

-- ---
-- Table Properties
-- ---

-- ALTER TABLE `users` ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_bin;
-- ALTER TABLE `feed_and_comunity` ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_bin;
-- ALTER TABLE `liked_contents` ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_bin;
-- ALTER TABLE `type_posts` ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_bin;

-- ---
-- Test Data
-- ---

-- INSERT INTO `users` (`id`,`name`,`email`,`password`,`State`) VALUES
-- ('','','','','');
-- INSERT INTO `feed_and_comunity` (`id`,`id_users`,`created_at`,`id_type_posts`,`project_title`,`project_description`,`project_duration`,`project_volunteers_quantity`) VALUES
-- ('','','','','','','','');
-- INSERT INTO `liked_contents` (`id`,`id_news_feed`,`id_users`) VALUES
-- ('','','');
-- INSERT INTO `type_posts` (`id`,`type_post`) VALUES
-- ('','');
```

