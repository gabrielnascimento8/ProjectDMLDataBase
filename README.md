Project data base university Unisa.

CREATE DATABASE ImovelADS_g;
GO

USE ImovelADS_g;
GO

CREATE TABLE estado(
sgEstado CHAR(2) NOT NULL PRIMARY KEY,
nmEstado VARCHAR(25) NOT NULL
);
GO

Insert Into estado
Values
('AC', 'Acre'),
('AL', 'Alagoas'),
('AP', 'Amapa'),
('AM', 'Amazonas'),
('BA', 'Bahia'),
('CE', 'Ceara'),
('ES', 'Espírito Santo'),
('GO', 'Goias'),
('MA', 'Maranhão'),
('MT', 'Mato Grosso'),
('MS', 'Mato Grosso do Sul'),
('MG', 'Minas Gerais'),
('PA', 'Pará'),
('PB', 'Paraiba'),
('PR', 'Parana'),
('PE', 'Pernambuco'),
('PI', 'Piaui'),
('RJ', 'Rio de Janeiro'),
('RN', 'Rio Grande do Norte'),
('RS', 'Rio Grande do Sul'),
('RO', 'Rondônia'),
('RR', 'Roraima'),
('SC', 'Santa Catarina'),
('SP', 'São Paulo'),
('SE', 'Sergipe'),
('TO', 'Tocantins'),
('DF', 'Distrito Federal');

GO

Select \*
From estado;
GO

CREATE TABLE cidade(
idCidade INTEGER NOT NULL PRIMARY KEY,
nmCidade VARCHAR(50) NOT NULL,
sgEstado CHAR(2) NOT NULL,
FOREIGN KEY(sgEstado)
REFERENCES estado(sgEstado)
);
GO

Insert Into cidade
Values
('1', 'Rio Branco', 'AC'),
('2', 'Cruzeiro do Sul','AC'),
('3', 'Plácido de Castro','AC'),
('4', 'Maceió', 'AL'),
('5', 'Arapiraca', 'AL'),
('6', 'São Miguel dos Campos', 'AL'),
('7', 'Macapá' ,'AP'),
('8', 'Santana', 'AP'),
('9', 'Ferreira Gomes','AP'),
('10', 'Manaus', 'AM'),
('11', 'Parintins', 'AM'),
('12', 'Itacoatiara','AM'),
('13', 'Salvador','BA'),
('14', 'Feira de Santana', 'BA'),
('15', 'Camaçari','BA'),
('16', 'Fortaleza', 'CE'),
('17', 'Caucaia' , 'CE'),
('18', 'Maracanau', 'CE'),
('19', 'Vitoria','ES'),
('20', 'Serra', 'ES'),
('21', 'Viana', 'ES'),
('22', 'Goiânia', 'GO'),
('23', 'Aparecida de Goiânia', 'GO'),
('24', 'Anápolis', 'GO'),
('25', 'São Luiz', 'MA'),
('26', 'Imperatriz', 'MA'),
('27', 'Santa Ines', 'MA'),
('28', 'Cuiabá', 'MT'),
('29', 'Várzea Grande', 'MT'),
('30', 'Rondonópolis', 'MT'),
('31', 'Campo Grande', 'MS'),
('32', 'Dourados', 'MS'),
('33', 'Ponta Pora', 'MS'),
('34', 'Belo Horizonte', 'MG'),
('35', 'Uberlândia', 'MG'),
('36', 'Montes Claros', 'MG'),
('37', 'Belém', 'PA'),
('38', 'Ananindeua', 'PA'),
('39', 'Castanhal', 'PA'),
('40', 'João Pessoa', 'PB'),
('41', 'Campina Grande', 'PB'),
('42', 'Santa Rita', 'PB'),
('43', 'Curitiba', 'PR'),
('44', 'Londrina', 'PR'),
('45', 'Maringa', 'PR'),
('46', 'Recife', 'PE'),
('47', 'Jaboatão dos Guararapes', 'PE'),
('48', 'Gravatá', 'PE'),
('49', 'Teresina', 'PI'),
('50', 'Parnaíba', 'PI'),
('51', 'Campo Maior', 'PI'),
('52', 'Rio de Janeiro', 'RJ'),
('53', 'São Gonçalo', 'RJ'),
('54', 'Petrópolis', 'RJ'),
('55', 'Natal', 'RN'),
('56', 'Mossoró', 'RN'),
('57', 'Parnamirim', 'RN'),
('58', 'Porto Alegre', 'RS'),
('59', 'Caxias do Sul', 'RS'),
('60', 'Pelotas', 'RS'),
('61', 'Porto Velho', 'RO'),
('62', 'Ji-Paraná', 'RO'),
('63', 'Ariquemes', 'RO'),
('64', 'Boa Vista', 'RR'),
('65', 'Rorainópolis', 'RR'),
('66', 'Normandia', 'RR'),
('67', 'Joinville', 'SC'),
('68', 'Florianópolis', 'SC'),
('69', 'Blumenau', 'SC'),
('70', 'São Paulo', 'SP'),
('71', 'Guarulhos', 'SP'),
('72', 'Campinas', 'SP'),
('73', 'Aracaju', 'SE'),
('74', 'Nossa Senhora do Socorro', 'SE'),
('75', 'Estancia', 'SE'),
('76', 'Palmas', 'TO'),
('77', 'Araguaína', 'TO'),
('78', 'Gurupi', 'TO'),
('79', 'Ceilândia', 'DF'),
('80', 'Samambaia', 'DF'),
('81', 'Taguatinga', 'DF');
GO

Select \*
From cidade;
GO

CREATE TABLE bairro(
idBairro INTEGER NOT NULL PRIMARY KEY,
nmBairro VARCHAR(50) NOT NULL,
idCidade INTEGER NOT NULL,
sgEstado CHAR(2) NOT NULL,
FOREIGN KEY(idCidade)
REFERENCES cidade(idCidade),
FOREIGN KEY(sgEstado)
REFERENCES estado(sgEstado)
);
GO

Insert Into bairro
Values

('1', 'Aviário' ,' 1' ,'AC'),
('2', 'Bosque' ,'1' ,'AC'),
('3', 'João Alves' ,'2' ,'AC'),
('4', 'Morro da Glória','2' ,'AC'),
('5', 'Olaria' ,'3' ,'AC'),
('6', 'Centro' ,'3' ,'AC'),
('7', 'Centro' ,'4' ,'AL'),
('8', 'Jaraguá' ,'4' ,'AL'),
('9', 'Ouro Preto' ,'5' ,'AL'),
('10', 'Primavera' ,'5' ,'AL'),
('11', 'Bairro de Fatima' ,'6' ,'AL'),
('12', 'Paraíso' ,'6' ,'AL'),
('13', 'Santa Rita' ,'7' ,'AP'),
('14', 'Central' ,'7' ,'AP'),
('15', 'Universidade' ,'8' ,'AP'),
('16', 'Novo Horizonte' ,'8','AP'),
('17', 'Congos' ,'9' ,'AP'),
('18', 'Buritizal' ,'9' ,'AP'),
('19', 'Cidade Nova' ,'10' ,'AM'),
('20', 'Flores' ,'10' ,'AM'),
('21', 'Palmares' ,'11' ,'AM'),
('22', 'São Francisco' ,'11' ,'AM'),
('23', 'Prainha' ,'12' ,'AM'),
('24', 'São Cristóvão' ,'12' ,'AM'),
('25', 'Brotas' ,'13' ,'BA'),
('26', 'Federação' ,'13' ,'BA'),
('27', 'Serraria Brasil' ,'14' ,'BA'),
('28', 'Santa Monica' ,'14' ,'BA'),
('29', 'Centro' ,'15' ,'BA'),
('30', 'Dois de Julho' ,'15' ,'BA'),
('31', 'Meireles' ,'16' ,'CE'),
('32', 'Aldeota' ,'16' ,'CE'),
('33', 'Vila Goes' ,'17' ,'CE'),
('34', 'Padre Romualdo','17' ,'CE'),
('35', 'Piratininga' ,'18' ,'CE'),
('36', 'Novo Maracanaú' ,'18' ,'CE'),
('37', 'Santa Clara' ,'19' ,'ES'),
('38', 'Vitoria Rubim' ,'19' ,'ES'),
('39', 'Jardim Bela Vista' ,'20' ,'ES'),
('40', 'São Domingos' ,'20' ,'ES'),
('41', 'Eldorado' ,'21' ,'ES'),
('42', 'Campo Verde' ,'21' ,'ES'),
('43', 'Jardim America' ,'22' ,'GO'),
('44', 'Jardim Atlântico' ,'22' ,'GO'),
('45', 'Vera Cruz' ,'23' ,'GO'),
('46', 'Jardim Belo Horizonte' ,'23' ,'GO'),
('47', 'Vila Santana' ,'24' ,'GO'),
('48', 'Vila Santa Isabel' ,'24','GO'),
('49', 'Jardim Eldorado' ,'25','MA'),
('50', 'Jardim Renascença','25','MA'),
('51', 'Santa Rita' ,'26' ,'MA'),
('52', 'Nova Imperatriz','26' ,'MA'),
('53', 'Centro' ,'27' ,'MA'),
('54', 'Raposa' ,'27' ,'MA'),
('55', 'Centro Norte' ,'28' ,'MT'),
('56', 'Bandeirantes' ,'28' ,'MT'),
('57', 'Centro Sul' ,'29' ,'MT'),
('58', 'Jardim Imperador' ,'29','MT'),
('59', 'Centro' ,'30' ,'MT'),
('60', 'Vila Planalto' ,'30' ,'MT'),
('61', 'Vila Gloria' ,'31' ,'MS'),
('62', 'Vila Carvalho' ,'31' ,'MS'),
('63', 'Centro' ,'32' ,'MS'),
('64', 'Jardim America' ,'32' ,'MS'),
('65', 'Vila Torres' ,'33' ,'MS'),
('66', 'Centro' ,'33' ,'MS'),
('67', 'Lourdes' ,'34' ,'MG'),
('68', 'Savassi' ,'34' ,'MG'),
('69', 'Martins' ,'35' ,'MG'),
('70', 'Centro' ,'35' ,'MG'),
('71', 'Centro' ,'36' ,'MG'),
('72', 'Candida Camara','36' ,'MG'),
('73', 'Campina' ,'37' ,'PA'),
('74', 'Jurunas' ,'37' ,'PA'),
('75', 'Centro' ,'38' ,'PA'),
('76', 'Cidade Nova' ,'38' ,'PA'),
('77', 'Pirapora' ,'39' ,'PA'),
('78', 'Caiçara' ,'39' ,'PA'),
('79', 'Jaguaribe' ,'40' ,'PB'),
('80', 'Estados' ,'40' ,'PB'),
('81', 'Centro' ,'41' ,'PB'),
('82', 'Lauritzen' ,'41' ,'PB'),
('83', 'Marcos Moura', '42' ,'PB'),
('84', 'Vila Tibiri' ,'42' ,'PB'),
('85', 'Centro' ,'43' ,'PR'),
('86', 'Rebouças' ,'43' ,'PR'),
('87', 'Vila Brasil' ,'44' ,'PR'),
('88', 'Centro' ,'44' ,'PR'),
('89', 'Zona 03' ,'45' ,'PR'),
('90', 'Zona 01' ,'45' ,'PR'),
('91', 'Soledade' ,'46' ,'PE'),
('92', 'Boa Vista' ,'46' ,'PE'),
('93', 'Centro' ,'47' ,'PE'),
('94', 'Vista Alegre' ,'47' ,'PE'),
('95', 'Centro' ,'48' ,'PE'),
('96', 'Cruzeiro' ,'48' ,'PE'),
('97', 'Piçarra' ,'49' ,'PI'),
('98', 'Cristo Rei' ,'49' ,'PI'),
('99', 'São Benedito' ,'50' ,'PI'),
('100', 'Boa Esperança' ,'50' ,'PI'),
('101','Centro' ,'51' ,'PI'),
('102', 'Flores' ,'51' ,'PI'),
('103', 'Centro' ,'52' ,'RJ'),
('104', 'Santa Teresa' ,'52' ,'RJ'),
('105', 'Vila Yara' ,'53' ,'RJ'),
('106', 'Rosane' ,'53' ,'RJ'),
('107', 'Centro' ,'54' ,'RJ'),
('108', 'Valparaiso' ,'54' ,'RJ'),
('109', 'Petrópolis' ,'55' ,'RN'),
('110', 'Areia Preta' ,'55' ,'RN'),
('111', 'Nova Betânia' ,'56' ,'RN'),
('112', 'Abolição' ,'56' ,'RN'),
('113', 'Boa Esperança' ,'57','RN'),
('114', 'Centro' ,'57' ,'RN'),
('115', 'Cidade Baixa' ,'58' ,'RS'),
('116', 'Bom Fim' ,'58' ,'RS'),
('117', 'Centro' ,'59' ,'RS'),
('118', 'Panazzolo' ,'59' ,'RS'),
('119', 'Tres Vendas' ,'60' ,'RS'),
('120', 'Jardim Europa' ,'60' ,'RS'),
('121', 'Centro' ,'61' ,'RO'),
('122', 'Mocambo' ,'61' ,'RO'),
('123', 'Jardim dos Imigrantes' ,'62','RO'),
('124', 'Bela Vista' ,'62' ,'RO'),
('125', 'Jardim Europa' ,'63' ,'RO'),
('126', 'Bela Vista' ,'63' ,'RO'),
('127', 'São Vicente' ,'64' ,'RR'),
('128', 'Mecejana' ,'64' ,'RR'),
('129', 'Nova Brasil' ,'65' ,'RR'),
('130', 'Pantanal' ,'65' ,'RR'),
('131', 'Centro' ,'66' ,'RR'),
('132', 'Centro' ,'66' ,'RR'),
('133', 'Anita Garibaldi','67' ,'SC'),
('134', 'Centro' ,'67' ,'SC'),
('135', 'Trindade' ,'68' ,'SC'),
('136', 'Centro' ,'68' ,'SC'),
('137', 'Victor Konder' ,'69' ,'SC'),
('138', 'Centro' ,'69' ,'SC'),
('139', 'Aclimação' ,'70' ,'SP'),
('140', 'Liberdade' ,'70' ,'SP'),
('141', 'Vila Progresso' ,'71' ,'SP'),
('142', 'Cidade Maia' ,'71' ,'SP'),
('143', 'Centro' ,'72' ,'SP'),
('144', 'Botafogo' ,'72' ,'SP'),
('145', 'São José' ,'73' ,'SE'),
('146', 'Salgado Filho' ,'73' ,'SE'),
('147', 'Albano Franco' ,'74' ,'SE'),
('148', 'Marcos Freire I' ,'74' ,'SE'),
('149', 'Alagoas' ,'75' ,'SE'),
('150', 'Centro' ,'75' ,'SE'),
('151', 'Plano Diretor Sul','76','TO'),
('152', 'Plano Diretor Norte','76','TO'),
('153', 'ST.Central' ,'77','TO'),
('154', 'Senador','77','TO'),
('155', 'Alto dos Buritis','78' ,'TO'),
('156', 'Jardim Tocantins','78' ,'TO'),
('157', 'Ceilândia Norte','79' ,'DF'),
('158', 'ST.M Norte' ,'79' ,'DF'),
('159', 'Centro Urbano' ,'80' ,'DF'),
('160', 'Conj.B' ,'80' ,'DF'),
('161', 'Taguatinga Norte','81' ,'DF'),
('162', 'St Hab Vicente Pires','81','DF');
GO

Select \*
From bairro;
GO

CREATE TABLE comprador(
idComprador INTEGER NOT NULL PRIMARY KEY,
nmComprador VARCHAR(50) NOT NULL,
nmEnderecoComprador VARCHAR(100) NOT NULL,
nrCPFComprador NUMERIC(11,0) NOT NULL,
idCidade INTEGER NOT NULL,
idBairro INTEGER NOT NULL,
sgEstado CHAR(2) NOT NULL,
telComprador NUMERIC(11,0) NOT NULL,
FOREIGN KEY(idCidade)
REFERENCES cidade(idCidade),
FOREIGN KEY(idBairro)
REFERENCES bairro(idBairro),
FOREIGN KEY(sgEstado)
REFERENCES estado(sgEstado)
);
GO

Insert Into comprador
Values
('1', 'Luzia Daiane Moura','Rua Pina Pinto 843','29867597427','1','2','AC','68982581722'),
('2', 'Roberto Vitor Bernardes','Caminho 24','80563438304', '2','2' ,'AC','68992800171'),
('3', 'Enrico Ruan Daniel da Roch','Rua Oracílio Martins Gonçalves 439','85278906820', '34','67','MG','31993302498'),
('4', 'Lara Elza Tânia Oliveira','Avenida Nicomedes Alves dos Santos 340','32090161434','35','69','MG','3432308810'),
('5', 'Maite Sonia Monteiro','Rua Ruben Berta 947', '42611527011','58','115','RS','51983757684'),
('6', 'Fiipe Geraldo Silveira', 'Rua Margarida Borelli 200','65339729877','59','117','RS','54984373739'),
('7', 'Raul Luis Peixoto', 'Rua João Ramos 355', '59159546182','52','103','RJ','21983093750'),
('8', 'Lorenzo Antonio da Cruz','Rua Manuel Duarte 223','76944536307','53','105','RJ','21983407494'),
('9', 'Diogo Marcelo Levi Assuncao','Rua Pires da Mota 234','64955235050','70','139','SP','11987750534'),
('10','Benedito Lorenzo Pinto','Rua Soldado Eurípedes Rodrigues de Lima 548','46877489373','71','141','SP','19981522041');

GO

Select \*
From comprador;
GO

CREATE TABLE vendedor(
idVendedor INTEGER NOT NULL PRIMARY KEY,
nmVendedor VARCHAR(50) NOT NULL,
nmEnderecoVendedor VARCHAR(100) NOT NULL,
nrCPFVendedor NUMERIC(11,0) NOT NULL,
idCidade INTEGER NOT NULL,
idBairro INTEGER NOT NULL,
sgEstado CHAR(2) NOT NULL,
telComprador NUMERIC(11,0) NOT NULL,
dtNasc DATE NOT NULL,
FOREIGN KEY(idCidade)
REFERENCES cidade(idCidade),
FOREIGN KEY(idBairro)
REFERENCES bairro(idBairro),
FOREIGN KEY(sgEstado)
REFERENCES estado(sgEstado)
);
GO

Insert Into vendedor
Values
('1', 'Gabrielly Camila Benedita Rodrigues', 'Rua Jornalista João José Torres 298', '17051372882','1','1','AC','68986880369','26/05/1974'),
('2', 'Simone Rebeca Almeida','Rua dos Maçons 632','38238243840','3','3','AC','68998772732','02/03/1980'),
('3', 'Enzo Bryan Ribeiro','Rua dos Flocos 459','18364108085', '34','67','MG','31999647895', '19/08/1957'),
('4', 'Agatha Manuela Caldeira','Rua Parimetral 617','82969443910','35', '69','MG','34981262909', '13/11/1994'),
('5', 'Kaique Benjamin Isaac Ferreira', 'Avenida Rachel Wolfrid 214', '87110771407','58','115', 'RS', '51987531596','02/03/1975'),
('6', 'Nathan Cláudio Castro','Rua Dante Michelon 723','62932445162', '59','117','RS','54999404673','18/11/1971'),
('7', 'Vitória Débora Aurora Jesus', 'Rua Paranagua 523','29033819333','67','133','SC','47993279042','17/04/1960'),
('8', 'Thales Theo Rodrigues','Rua Pedro Alexandrino 808','40491758863','68','135','SC','48991037288','23/08/1965'),
('9', 'Vinicius Roberto Melo','Rua Florentina Fernandes Camargo 345', '10200172603','43','85','PR','41987662082','21/11/1953'),
('10', 'Emanuel Vitor da Conceição','Rua Serra Fria 495','80405110545','44','89','PR','43988445835','21/06/1947'),
('11', 'Francisca Regina Moraes','Rua Espirito Santo 348','83103896123','70','139','SP','11988899726','15/09/1966'),
('12', 'Bernardo Igor Ribeiro','Rua Vitória da Conquista 287', '57166895586','71','141','SP','19998304412','14/04/1968'),
('13', 'Heitor Nelson Manoel Sales','Rua Coruja 720','51737102412','52','103','RJ','21989744515','13/01/1972'),
('14', 'Heloisa Sebastiana Cláudia Baptista','Rua Dona Laura 270', '25669217845', '53','105','RJ','22992918195','07/12/1990'),
('15', 'Eduarda Elza Assunção', 'Rua José Miranda Sobrinho 240','60014774690', '19','37','ES', '27991442899', '18/01/1988');

GO

Select \*
From vendedor;
GO

CREATE TABLE imovel(
idImovel INTEGER NOT NULL PRIMARY KEY,
idVendedor INTEGER NOT NULL,
idBairro INTEGER NOT NULL,
idCidade INTEGER NOT NULL,
sgEstado CHAR(2) NOT NULL,
nmEnderecoImovel VARCHAR(100) NOT NULL,
nrAreaUtil DECIMAL(7,2) NOT NULL,
nrAreaTotal DECIMAL(7,2) NOT NULL,
vlPreco DECIMAL(11,2) NOT NULL,
stVendido CHAR(1) NOT NULL,
dtLancto DATE NOT NULL,
FOREIGN KEY(idVendedor)
REFERENCES vendedor(idVendedor),
FOREIGN KEY(idBairro)
REFERENCES bairro(idBairro),
FOREIGN KEY(idCidade)
REFERENCES cidade(idCidade),
FOREIGN KEY(sgEstado)
REFERENCES estado(sgEstado)
);
GO

Insert Into imovel
Values

(1, 1, 1, 1, 'AC', 'Rua Antimari 414', 51, 60, 170.000, '0', '10/10/2021'),
(2, 1, 2, 1, 'AC', 'Rua Alvorada 54', 375, 43, 1.600, '0', '11/10/2021'),
(3, 1, 3, 2, 'AC', 'Rua Nilo Peçanha 518', 64, 50, 110.000, '0', '12/10/2021'),
(4, 1, 4, 2, 'AC', 'Rua Floriano Peixoto 189', 319, 686, 350.000, '0', '13/10/2021'),
(5, 1, 5, 3, 'AC', 'Rua Raimunda Pena 81', 240, 500, 200.000, '0', '14/10/2021'),
(6, 1, 6, 3, 'AC', 'Rua Wilson Tendro Carvalho 108', 360, 785, 400.000, '0', '15/10/2021'),
(7, 1, 7, 4, 'AL', 'Rua Guido Duarte 70', 900, 1500, 2.500000, '0', '16/10/2021'),
(8, 1, 8, 4, 'AL', 'Rua Sá e Albuquerque 372', 540, 980, 600.000, '0', '17/10/2021'),
(9, 1, 9, 5, 'AL', 'Rua Tibúrcio Magalhães 75',  1000, 45300, 500.000, '0', '18/10/2021'),
(10, 1, 10, 5, 'AL', 'R. Est. José Acácio 560', 550, 1800, 550.000, '0', '19/10/2021'),
(11, 1, 11, 6, 'AL', 'R. São Pedro 98', 450, 880, 300.000, '0', '20/10/2021'),
(12, 2, 12, 6, 'AL', 'R. José Medeiros Aprato 60', 200, 400, 235.000, '0', '21/10/2021'),
(13, 2, 13, 7, 'AP', 'Avenida José Caetano 1667', 497, 950, 135.000, '0', '22/10/2021'),
(14, 2, 14, 7, 'AP', 'Rua Eliezer Levi 1981', 540, 1900, 1.200000, '0', '23/10/2021'),
(15, 2, 15, 8, 'AP', 'Rua Inspetor Marcelino 579', 360, 545, 75.000, '0', '24/10/2021'),
(16, 2, 16, 8, 'AP', 'Rua Alceu Paulo Ramos 2772', 540, 790, 1.200000, '0', '25/10/2021'),
(17, 2, 17, 9, 'AP', 'Rua Dr Alberto Lima 123', 5264, 9589, 1.300000, '0', '26/10/2021'),
(18, 2, 18, 9, 'AP', 'Avenida dos Guaranis 232', 350, 620, 750.000, '0', '27/10/2021'),
(19, 2, 19, 10, 'AM', 'Rua Miquerinos 257', 275, 590, 295.000, '0', '28/10/2021'),
(20, 2, 20, 10, 'AM', 'Rua Maracaibo 8', 240, 710, 480.000, '0', '29/10/2021'),
(21, 2, 21, 11, 'AM', 'Rua Paraiba 800', 300, 860, 500.000, '0', '30/10/2021'),
(22, 2, 22, 11, 'AM', 'Rua Sete de Setembro 2388', 244, 690, 490.000, '0', '31/10/2021'),
(23, 3, 23, 12, 'AM', 'Rua Sabia 100', 750, 1200, 300.000, '0', '01/11/2021'),
(24, 3, 24, 12, 'AM', 'Rua Moacir Abreu 3667', 349, 995, 120.000, '0', '02/11/2021'),
(25, 3, 25, 13, 'BA', 'Rua Pedro Molhado 96', 211, 688, 850.000, '0', '03/11/2021'),
(26, 3, 26, 13, 'BA', 'Rua Engenheiro Jaime Zaverucha 25', 150, 550, 210.000, '0', '04/11/2021'),
(27, 3, 27, 14, 'BA', 'Avenida Senador Quintino 836', 53, 200, 220.000, '0', '05/11/2021'),
(28, 3, 28, 14, 'BA', 'Rua Cosme e Damião 600', 110, 380, 355.000, '0', '06/11/2021'),
(29, 3, 29, 15, 'BA', 'Rua Franscico Drumond 40', 137, 450, 550.000, '0', '07/11/2021'),
(30, 3, 30, 15, 'BA', 'Rua Nova Esperança 419', 376, 670, 2.100000, '0', '08/11/2021'),
(31, 3, 31, 16, 'CE', 'Avenida da Abolição 2066', 222, 252, 3.200, '0', '09/11/2021'),
(32, 3, 32, 16, 'CE', 'Rua Vicente Linhares 521', 177, 177, 900.000, '0', '10/11/2021'),
(33, 3, 33, 17, 'CE', 'Rua Parque Lagoinha 17', 74, 100, 180.000, '0', '11/11/2021'),
(34, 4, 34, 17, 'CE', 'Rua Dois 137', 50, 50, 110.000, '0', '12/11/2021'),
(35, 4, 35, 18, 'CE', 'Rua Manaus 499', 200, 200, 1.000000, '0', '13/11/2021'),
(36, 4, 36, 18, 'CE', 'Avenida Oeste 456', 320, 320, 1.250000, '0', '14/11/2021'),
(37, 4, 37, 19, 'ES', 'Rua Santa Clara 260', 115, 115, 350.000, '0', '15/11/2021'),
(38, 4, 38, 19, 'ES', 'Avenida Duarte Lemos 61', 80, 80, 250.000, '0', '16/11/2021'),
(39, 4, 39, 20, 'ES', 'Avenida Contorno 57', 97, 97, 600.000, '0', '17/11/2021'),
(40, 4, 40, 20, 'ES', 'Rua Santo Antonio 211', 85, 85, 370.000, '0', '18/11/2021'),
(41, 4, 41, 21, 'ES', 'Rua Rio Doce 13', 116, 116, 850.000000, '0', '19/11/2021'),  
(42, 4, 42, 21, 'ES', 'Rua Versuvio 28', 46, 46, 375.000, '0', '20/11/2021'),
(43, 4, 43, 22, 'GO', 'Avenida C 104, 1236', 117, 117, 190.000, '0', '21/11/2021'),
(44, 4, 44, 22, 'GO', 'Rua da Charita 2154', 250, 250, 450.000, '0', '22/11/2021'),
(45, 5, 45, 23, 'GO', 'Rua Uberlandia 112', 210, 210, 350.000, '0', '23/11/2021'),
(46, 5, 46, 23, 'GO', 'Rua Salvador Q38 0', 143, 143, 270.000, '0', '24/11/2021'),
(47, 5, 47, 24, 'GO', 'Rua Sen Alfredo Nasser 140', 250, 250, 1.200000, '0', '25/11/2021'),
(48, 5, 48, 24, 'GO', 'Avenida universitaria 1790', 315, 315, 190.000, '0', '26/11/2021'),
(49, 5, 49, 25, 'MA', 'Avenida um 13', 500, 500, 3.600000, '0', '27/11/2021'),
(50, 5, 50, 25, 'MA', 'Rua Graunas 2', 563, 563, 720.000, '0', '28/11/2021'),
(51, 5, 51, 26, 'MA', 'Avenida Industrial 112', 110, 110, 350.000, '0', '29/11/2021'),
(52, 5, 52, 26, 'MA', 'Rua Pernambuco 1203', 77, 77, 390.000, '0', '30/11/2021'),
(53, 5, 53, 27, 'MA', 'Rua do Cordeiro 392', 140, 140, 360.000, '0', '01/12/2021'),
(54, 5, 54, 27, 'MA', 'Rua do Cajueiro 178', 110, 110, 390.000, '0', '02/12/2021'),
(55, 5, 55, 28, 'MT', 'Rua Voluntarios da Patria 350', 51, 51, 135.000, '0', '03/12/2021'),
(56, 6, 56, 28, 'MT', 'Rua Alberto Velho Moreira 202', 184, 184, 125.000, '0', '04/12/2021'),
(57, 6, 57, 29, 'MT', 'Rua Cap Costa 208', 62, 62, 170.000, '0', '05/12/2021'),
(58, 6, 58, 29, 'MT', 'Rua Rui Barbosa 409', 157, 157, 180.000, '0', '06/12/2021'),
(59, 6, 59, 30, 'MT', 'Avenida Cuiaba 1070', 170, 170, 190.000, '0', '07/12/2021'),
(60, 6, 60, 30, 'MT', 'Rua Dois 99', 155, 155, 220.000, '0', '08/12/2021'),
(61, 6, 61, 31, 'MS', 'Rua Rui Barbosa 1570', 451, 451, 1.800000, '0', '09/12/2021'),
(62, 6, 62, 31, 'MS', 'Rua Shoei Arakaki 266', 206, 206, 255.000, '0', '10/12/2021'),
(63, 6, 63, 32, 'MS', 'Rua Onofre Pereira de Matos 970', 372, 373, 595.000, '0', '11/12/2021'),
(64, 6, 64, 32, 'MS', 'Rua Marques Oliveira 1065', 70, 70, 320.000, '0', '12/12/2021'),
(65, 6, 65, 33, 'MS', 'Rua Calogeras 428', 75, 79, 350.000, '0', '13/12/2021'),
(66, 6, 66, 33, 'MS', 'Rua Marechal Floreano 2310', 150, 150, 285.000, '0', '14/12/2021'),
(67, 7, 67, 34, 'MG', 'Rua São Paulo 1905', 120, 120, 275.000, '0', '15/12/2021'),
(68, 7, 68, 34, 'MG', 'Rua dos Inconfidentes 911', 63, 63, 200.000, '0', '16/12/2021'),
(69, 7, 69, 35, 'MG', 'Rua Professor João Basilio 269', 121, 121, 270.000, '0', '17/12/2021'),
(70, 7, 70, 35, 'MG', 'Avenida João Pessoa 16', 250, 250, 470.000, '0', '18/12/2021'),
(71, 7, 71, 36, 'MG', 'Rua João Pinheiro 11', 360, 360, 800.000, '0', '19/12/2021'),
(72, 7, 72, 36, 'MG', 'Rua Raul Correa 260', 250, 250, 240.000, '0', '20/12/2021'),
(73, 7, 73, 37, 'PA', 'Rua Santo Antonio 117', 210, 210, 600.000, '0', '21/12/2021'),
(74, 7, 74, 37, 'PA', 'Rua dos Caripunas 639', 180, 180, 700.000, '0', '22/12/2021'),
(75, 7, 75, 38, 'PA', 'Avenida Claudio Sanders 980', 172, 172, 550.000, '0', '23/12/2021'),
(76, 7, 76, 38, 'PA', 'Tv SN 03 1331', 244, 244, 391.360, '0', '24/12/2021'),
(77, 7, 77, 39, 'PA', 'Rua Eusebio Foreliza 1209', 400, 400, 600.000, '0', '25/12/2021'),
(78, 8, 78, 39, 'PA', 'Alameda Imperial 1019', 43, 43, 160.000, '0', '26/12/2021'),
(79, 8, 79, 40, 'PB', 'Avenida Primeiro de Maio 239', 86, 86, 250.000, '0', '27/12/2021'),
(80, 8, 80, 40, 'PB', 'Avenida Alagoas 624', 90, 90, 230.000, '0', '28/12/2021'),
(81, 8, 81, 41, 'PB', 'Rua Vidal Negreiros 126', 293, 293, 850.000, '0', '29/12/2021'),
(82, 8, 82, 41, 'PB', 'Rua Antonio Campos 66', 360, 360, 1.100000, '0', '30/12/2021'),
(83, 8, 83, 42, 'PB', 'Rua Luis Francisco da Costa 192', 62, 62, 100.000, '0', '31/12/2021'),
(84, 8, 84, 42, 'PB', 'Rua Euripedes Tavares 446', 129, 129, 180.000, '0', '01/01/2022'),
(85, 8, 85, 43, 'PR', 'Rua Emiliano Perneta 288', 246, 246, 575.000, '0', '02/01/2022'),
(86, 8, 86, 43, 'PR', 'Rua 24 de Maio 1160', 239, 239, 770.000, '0', '03/01/2022'),
(87, 8, 87, 44, 'PR', 'Rua Bolivia 426', 338, 338, 710.000, '0', '04/01/2022'),
(88, 8, 88, 44, 'PR', 'Rua Piauí 399', 350, 350, 500.000, '0', '05/01/2022'),
(89, 9, 89, 45, 'PR', 'Rua Marcilio Dias 1068', 182, 182, 750.000, '0', '06/01/2022'),
(90, 9, 90, 45, 'PR', 'Rua Joubert de Carvalho 683', 113, 113, 620.000, '0', '07/01/2022'),
(91, 9, 91, 46, 'PE', 'Avenida Oliveira Lima 1029', 150, 150, 335.000, '0', '08/01/2022'),
(92, 9, 92, 46, 'PE', 'Rua Cap Rui Lucena 71', 91, 91, 240.000, '0', '09/01/2022'),
(93, 9, 93, 47, 'PE', 'Rua Frei Caneca 263', 200, 200, 490.000, '0', '10/01/2022'),
(94, 9, 94, 47, 'PE', 'Rua Princesa Isabel 39', 258, 258, 1.830000, '0', '11/01/2022'),
(95, 9, 95, 48, 'PE', 'Rua Quininha matoso 181', 300, 300, 500.000, '0', '12/01/2022'),
(96, 9, 96, 48, 'PE', 'Avenida Um 14', 260, 260, 480.000, '0', '13/01/2022'),
(97, 9, 97, 49, 'PI', 'Avenida São Raimundo 154 C', 260, 260, 970.000, '0', '14/01/2022'),
(98, 9, 98, 49, 'PI', 'Avenida Abdias Neves 1520', 360, 360, 1.850000, '0', '15/01/2022'),
(99, 9, 99, 50, 'PI', 'Rua Virgilio Antunes 102', 750, 750, 400.000, '0', '16/01/2022'),
(100, 10, 100, 50, 'PI', 'Avenida Dr João Silva Filho 1200', 450, 450, 350.000, '0', '17/01/2022'),
(101, 10, 101, 51, 'PI', 'Rua Padre Manoel Felix 385', 120, 120, 75.000, '0', '18/01/2022'),
(102, 10, 102, 51, 'PI', 'Rua Mandube 343', 73, 73, 50.986, '0', '19/01/2022'),
(103, 10, 103, 52, 'RJ', 'Rua Mexico 168', 88, 88, 260.000, '0', '20/01/2022'),
(104, 10, 104, 52, 'RJ', 'Rua Eduardo Santos 38', 168, 173, 350.000, '0', '21/01/2022'),
(105, 10, 105, 53, 'RJ', 'Tv Frnacisco Malafaia 49', 200, 200, 280.000, '0', '22/01/2022'),
(106, 10, 106, 53, 'RJ', 'Rua Candido Mota Filho 150', 300, 300, 420.000, '0', '23/01/2022'),
(107, 10, 107, 54, 'RJ', 'Avenida Dom Pedro I 442', 80, 100, 320.000, '0', '24/01/2022'),
(108, 10, 108, 54, 'RJ', 'Rua Tem Queiros 114', 290, 100, 550.000, '0', '25/01/2022'),
(109, 10, 109, 55, 'RN', 'Rua Mipibu 419', 156, 156, 40.000, '0', '26/01/2022'),
(110, 10, 110, 55, 'RN', 'Rua Pinto Martins 1000', 33, 33, 60.000, '0', '27/01/2022'),
(111, 11, 111, 56, 'RN', 'Rua Antonio Vieira de Sa 380', 211, 211, 370.000, '0', '28/01/2022'),
(112, 11, 112, 56, 'RN', 'Rua Nisia Santiago 666', 240, 240, 260.000, '0', '29/01/2022'),
(113, 11, 113, 57, 'RN', 'Rua Manoel Costa 491', 60, 60, 39.000, '0', '30/01/2022'),
(114, 11, 114, 57, 'RN', 'Av Brig Everaldo Breves 152', 45, 45, 45.000, '0', '31/01/2022'),
(115, 11, 115, 58, 'RS', 'Rua João Alfredo 255', 340, 340, 2.990000, '0', '01/02/2022'),
(116, 11, 116, 58, 'RS', 'Rua Vasco da Gama 51', 300, 300, 1.800000, '0', '02/02/2022'),
(117, 11, 117, 59, 'RS', 'Rua Pinheiro Machado 1789', 81, 81, 379.000, '0', '03/02/2022'),
(118, 11, 118, 59, 'RS', 'Rua Santo Ceroni 175', 147, 147, 390.000, '0', '04/02/2022'),
(119, 11, 119, 60, 'RS', 'Rua Leonardo da Vinci 80', 42, 42, 100.000, '0', '05/02/2022'),
(120, 11, 120, 60, 'RS', 'Rua Quinze de Novembro 464', 47, 47, 128.000, '0', '06/02/2022'),
(121, 11, 121, 61, 'RO', 'Rua Treze de Maio 2132', 80, 80, 90.000, '0', '07/02/2022'),
(122, 12, 122, 61, 'RO', 'Av Sete de Setembro 941', 180, 180, 95.000, '0', '08/02/2022'),
(123, 12, 123, 62, 'RO', 'Rua Rio Branco 782', 508, 508, 450.000, '0', '09/02/2022'),
(124, 12, 124, 62, 'RO', 'Rua João dos Santos Filho 644', 500, 500, 800.000, '0', '10/02/2022'),
(125, 12, 125, 63, 'RO', 'Rua Suécia 3237', 90, 90, 60.000, '0', '11/02/2022'),
(126, 12, 126, 63, 'RO', 'Avenida Brasilia 4822', 100, 100, 120.000, '0', '12/02/2022'),
(127, 12, 127, 64, 'RR', 'Avenida Ville Roy 7984', 70, 70, 115.000, '0', '13/02/2022'),
(128, 12, 128, 64, 'RR', 'Rua Cristovao Coelho 705', 124, 124, 320.000, '0', '14/02/2022'),
(129, 12, 129, 65, 'RR', 'Rua Maranhão 200', 900, 900, 550.000, '0', '15/02/2022'),
(130, 12, 130, 65, 'RR', 'Rua Anaua 755', 1100, 1100, 275.000, '0', '16/02/2022'),
(131, 12, 131, 66, 'RR', 'Rua Manoel Amancio 3', 30, 30, 75.000, '0', '17/02/2022'),
(132, 13, 132, 66, 'RR', 'Rua Pedro Rodrigues 10', 200, 200, 55.000, '0', '18/02/2022'),
(133, 13, 133, 67, 'SC', 'Rua Porto União 550', 54, 54, 183.950, '0', '19/02/2022'),
(134, 13, 134, 67, 'SC', 'Rua do Principe 315', 31, 31, 279.950, '0', '20/02/2022'),
(135, 13, 135, 68, 'SC', 'Rua João Marçal 69', 400, 400, 6.200000, '0', '21/02/2022'),
(136, 13, 136, 68, 'SC', 'Rua Presidente Nereu Ramos 160', 840, 840, 12.800000, '0', '22/02/2022'),
(137, 13, 137, 69, 'SC', 'Rua Victor Konder 130', 73, 73, 235.000, '0', '23/02/2022'),
(138, 13, 138, 69, 'SC', 'Rua 7 de Setembro 2100', 87, 87, 290.000, '0', '24/02/2022'),
(139, 13, 139, 70, 'SP', 'Rua Jaspe 57', 247, 247, 1.590000, '0', '25/02/2022'),
(140, 13, 140, 70, 'SP', 'Rua Teixeira Leite 442', 460, 460, 5.900000, '0', '26/02/2022'),
(141, 13, 141, 71, 'SP', 'Rua Antonio Guedes da Silva 25', 140, 140, 650.000, '0', '27/02/2022'),
(142, 14, 142, 71, 'SP', 'Av Dr Carlos dos Campos 150', 45, 45, 170.000, '0', '28/02/2022'),
(143, 14, 143, 72, 'SP', 'Rua José Paulino 479', 220, 220, 450.000, '0', '01/03/2022'),
(144, 14, 144, 72, 'SP', 'Rua Cesario Mota 173', 136, 136, 500.000, '0', '02/03/2022'),
(145, 14, 145, 73, 'SE', 'Rua Riachuelo 100', 217, 217, 500.000, '0', '03/03/2022'),
(146, 14, 146, 73, 'SE', 'Rua Francisco Portugal 130 ', 180, 180, 180.000, '0', '04/03/2022'),
(147, 14, 147, 74, 'SE', 'Av Coletora C 146', 105, 105, 165.000, '0', '05/03/2022'),
(148, 14, 148, 74, 'SE', 'Rua 24 145', 100, 100, 170.000, '0', '06/03/2022'),
(149, 14, 149, 75, 'SE', 'Rua prof Jose Dias de Oliveira 86', 135, 135, 100.000, '0', '07/03/2022'),
(150, 14, 150, 75, 'SE', 'Rua João Café Filho 7', 65, 65, 100.000, '0', '08/03/2022'),
(151, 14, 151, 76, 'TO', 'Q 603 Sul Alameda 5 12', 257, 257, 950.000, '0', '09/03/2022'),
(152, 15, 152, 76, 'TO', 'Q 404 Norte Alameda 25', 88, 88, 495.000, '0', '10/03/2022'),
(153, 15, 153, 77, 'TO', 'R Santa Cruz 557', 405, 405, 75.000, '0', '11/03/2022'),
(154, 15, 154, 77, 'TO', 'R 6 185 85', 60, 60, 90.000, '0', '12/03/2022'),
(155, 15, 155, 78, 'TO', 'Av Territorio do Rio Branco 1122', 186, 186, 300.000, '0', '13/03/2022'),
(156, 15, 156, 78, 'TO', 'Rua 28 Q9 172', 303, 303, 900.000, '0', '14/03/2022'),
(157, 15, 157, 79, 'DF', 'Conj H', 200, 200, 390.000, '0', '15/03/2022'),
(158, 15, 158, 79, 'DF', 'Conj J', 310, 310, 170.000, '0', '16/03/2022'),
(159, 15, 159, 80, 'DF', 'Q302', 400, 400, 700.000, '0', '17/03/2022'),
(160, 15, 160, 80, 'DF', 'QS 408', 300, 300, 300.000, '0', '18/03/2022'),
(161, 15, 161, 81, 'DF', 'QND 56', 200, 200, 480.000, '0', '19/03/2022'),
(162, 15, 162, 81, 'DF', 'R 10', 100, 150, 380.000, '0', '20/03/2022');

GO

Select \*
From imovel;
GO

CREATE TABLE oferta(
idOferta INTEGER NOT NULL PRIMARY KEY,
idImovel INTEGER NOT NULL,
idComprador INTEGER NOT NULL,
vlOferta DECIMAL(11,2) NOT NULL,
dtOferta DATE NOT NULL,
FOREIGN KEY(idImovel)
REFERENCES imovel(idImovel),
FOREIGN KEY(idComprador)
REFERENCES comprador(idComprador)
);
GO

Insert Into oferta
Values

(1, 1, 1, 170.000, '10/10/2021'),
(2, 2, 1, 1.600, '11/10/2021'),
(3, 3, 1, 110.000, '12/10/2021'),
(4, 4, 1, 350.000, '13/10/2021'),
(5, 5, 2, 200.000, '14/10/2021'),
(6, 6, 2, 400.000, '15/10/2021'),
(7, 7, 2, 2.500000, '16/10/2021'),
(8, 8, 2, 600.000, '17/10/2021'),
(9, 9, 3, 3.500000, '18/10/2021'),
(10, 10, 3, 550.000, '19/10/2021'),
(11, 11, 3, 300.000, '20/10/2021'),
(12, 12, 3, 235.000, '21/10/2021'),
(13, 13, 4, 135.000, '22/10/2021'),
(14, 14, 4, 1.200000, '23/10/2021'),
(15, 15, 4, 75.000, '24/10/2021'),
(16, 16, 4, 1.200000, '25/10/2021'),
(17, 17, 5, 1.300000, '26/10/2021'),
(18, 18, 5, 750.000, '27/10/2021'),
(19, 19, 5, 295.000, '28/10/2021'),
(20, 20, 5, 480.000, '29/10/2021'),
(21, 21, 6, 500.000, '30/10/2021'),
(22, 22, 6, 490.000, '31/10/2021'),
(23, 23, 6, 300.000, '01/11/2021'),
(24, 24, 6, 120.000, '02/11/2021'),
(25, 25, 7, 850.000, '03/11/2021'),
(26, 26, 7, 210.000, '04/11/2021'),
(27, 27, 7, 220.000, '05/11/2021'),
(28, 28, 7, 355.000, '06/11/2021'),
(29, 29, 8, 550.000, '07/11/2021'),
(30, 30, 8, 2.100000, '08/11/2021'),
(31, 31, 8, 3.200, '09/11/2021'),
(32, 32, 8, 900.000, '10/11/2021'),
(33, 33, 9, 180.000, '11/11/2021'),
(34, 34, 9, 110.000, '12/11/2021'),
(35, 35, 9, 1.000000, '13/11/2021'),
(36, 36, 9, 1.250000, '14/11/2021'),
(37, 37, 10, 350.000, '15/11/2021'),
(38, 38, 10, 250.000, '16/11/2021'),
(39, 39, 10, 600.000, '17/11/2021'),
(40, 40, 10, 370.000, '18/11/2021'),
(41, 41, 10, 850.000, '19/11/2021'),
(42, 42, 10, 375.000, '20/11/2021'),
(43, 43, 10, 190.000, '21/11/2021'),
(44, 44, 10, 450.000, '22/11/2021'),
(45, 45, 10, 350.000, '23/11/2021'),
(46, 46, 10, 270.000, '24/11/2021'),
(47, 47, 10, 1.200000, '25/11/2021'),
(48, 48, 10, 190.000, '26/11/2021'),
(49, 49, 10, 3.600000, '27/11/2021'),
(50, 50, 10, 720.000, '28/11/2021');

GO

Select \*
From oferta;
GO

/_ALTER TABLE imovel
ADD FOREIGN KEY(idOferta)
REFERENCES oferta(idOferta);
GO_/

CREATE TABLE faixaImovel(
idFaixa INTEGER NOT NULL PRIMARY KEY,
nmFaixa VARCHAR (50) NOT NULL,
vlMinimo DECIMAL (8,2) NOT NULL,
vlMaximo DECIMAL (9,2) NOT NULL,
);
GO

--vlMinimo -> 100.000,00
--vlMaximo -> 5.000.000,00

Insert Into faixaImovel
Values
(1, 'Baixo', 0, 105000),
(2, 'Médio', 105001, 180000),
(3, 'Alto', 180001, 999999);

GO

SELECT \*
FROM faixaImovel;
GO
