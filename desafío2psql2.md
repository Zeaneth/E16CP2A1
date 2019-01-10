# 1. Crear base de datos
"""
CREATE DATABASE Pintagram;   
"""
# 1.1 Acceso a bd
"""
\c pintagram
"""
# 2 Crear tabla de Users
"""
CREATE TABLE users (
    id integer PRIMARY KEY,
    first_name VARCHAR (50) NOT NULL,
    last_name VARCHAR (50) NOT NULL,
    email VARCHAR (50) NOT NULL
);
"""
# Agregar 3 usuarios 
"""
INSERT INTO users (id, first_name, last_name, email) values (1,'Monica','Mambo','mmambo@gmail.com'),(2,'Erica','Number','enumber@gmail.com'),(3,'Rita','Five','rfive@gmail.com');
"""
# Crear tabla Image
"""
CREATE TABLE image (
    id INTEGER PRIMARY KEY,
    name VARCHAR NOT NULL,
    type VARCHAR NOT NULL,
    size FLOAT NOT NULL,
    owner_id INTEGER REFERENCES users(id)
);
"""
"""
INSERT INTO Post(id, description, writer_id) values (1,'genial',1)
INSERT INTO Post(id, description, writer_id) values (2,'genial',2)
INSERT INTO Post(id, description, writer_id) values (3,'genial',3)
"""
"""
CREATE TABLE Evaluated_post (
    id INTEGER PRIMARY KEY,
    id_post INTEGER REFERENCES Post(id),
    id_user INTEGER REFERENCES Users(id),
    like boolean
);
"""
"""
INSERT INTO Evaluated_post (id, id_post, id_user) values (1,1,1,0)
INSERT INTO Evaluated_post (id, id_post, id_user) values (2,2,2,1)
INSERT INTO Evaluated_post (id, id_post, id_user) values (3,3,3,0)
"""

