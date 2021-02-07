# RUN
0. just need copy ".dockerignore" & "docker-compose.yml" to your project's root path
1. `docker-compose up -d --build`

DIRECTORY STRUCTURE
-------------------

    PROJECTNAME
    └ logs
    └ mysql
    └ sessions
    └ www/codeigniter4
    └ .dockerignore & docker-compose.yml

# EDIT in "codeigniter4" folder
0. `www/codeigniter4/app/Config/Database.php`
+ NO need config DB
+ output DB connection on browser
```php
public function __construct() {
    ...
    else {
			echo json_encode($this->default);
		}
}
```

1. `www/codeigniter4/app/Controllers/Home.php`
+ test connect DB:
```php
public function index()
{
    // $fields = [
    // 	'id'          => [
    // 			'type'           => 'INT',
    // 			'constraint'     => 5,
    // 			'unsigned'       => true,
    // 			'auto_increment' => true
    // 	],
    // 	'title'       => [
    // 			'type'           => 'VARCHAR',
    // 			'constraint'     => '100',
    // 			'unique'         => true,
    // 	],
    // 	'author'      => [
    // 			'type'           =>'VARCHAR',
    // 			'constraint'     => 100,
    // 			'default'        => 'King of Town',
    // 	],
    // 	'description' => [
    // 			'type'           => 'TEXT',
    // 			'null'           => true,
    // 	],
    // 	'status'      => [
    // 			'type'           => 'ENUM',
    // 			'constraint'     => ['publish', 'pending', 'draft'],
    // 			'default'        => 'pending',
    // 	],
    // ];
    // $forge = \Config\Database::forge();
    // $forge->addField($fields);
    // $forge->addPrimaryKey('id');
    // $forge->addUniqueKey(['id']);

    // $forge->createTable('test');
    // dd($forge);
    
    return view('welcome_message');
}
```

2. `www/codeigniter4/.env` (COPY PASTE FROM "env")
+ edit setting config, for ex:
```php
CI_ENVIRONMENT = development
...
database.default.hostname = codeigniter4_mysql
database.default.database = codeigniter4
database.default.username = codeigniter4
database.default.password = codeigniter4
database.default.DBDriver = MySQLi
```
