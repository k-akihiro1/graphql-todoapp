# vscode 拡張機能
- GraphQL: Language Feature Support
- GraphQL: Syntax Highlighting
- Prisma
- React Extension Pack

# 環境構築
`yarn global add @nestjs/cli`  
`nest new backend :yarn`  
`yarn run start`

`cd backend`
配下に以下のリポジトリーを配置する  
https://github.com/k-akihiro1/graphql-todoapp-backend

`yarn add @nestjs/graphql @nestjs/apollo apollo-server-express graphql`

`yarn add @apollo/server`

# バリデーション
`yarn add class-transformer class-validator`  
https://github.com/typestack/class-validator#validation-decorators

# モジュールの作成

`nest g module task`

# サービスとリゾルバーの設定

`nest g resolver task --no-spec`  
`nest g service task --no-spec`

# 実行コマンド

`yarn start:dev`

PostgreSQL の CLI 接続コマンド  
`docker exec -it postgres psql -U udemy_user udemydb`

# 略語

`dto`: Data Transfer Object

参考文献：
https://docs.nestjs.com/graphql/quick-start#installation
https://zenn.dev/waddy/books/graphql-nestjs-nextjs-bootcamp/viewer/nestjs

### リクエストテンプレート

```
mutation createTask($createTaskInput: CreateTaskInput!){
createTask(
	createTaskInput: $createTaskInput
) {
    id
    name
    dueDate
    status
  	description
  }
}
```

```
{
  "createTaskInput": {
  	"name":  "test",
    "dueDate": "2024-01-01"
  }
}
```

### Prisma
`yarn add prisma --dev`  
https://www.prisma.io/docs/getting-started/quickstart
`yarn prisma init`  
.env と prisma/schema.prisma が作成される
Prismaで使用できる型は以下を参照  
https://www.prisma.io/docs/orm/reference/prisma-schema-reference#model-field-scalar-types

Prismaスキーマでは特に指定のない場合は、StringフィールドをTEXT型としてデータベースに保存される
VARCHAR型のフィールドの方がTEXT型のフィールドよりも検索やソートの操作が高速になる  
参考サイト： https://blog.to-ko-s.com/prisma-schema/

`yarn prisma migrate dev --name init`

`yarn prisma studio`

Prismaクライアントのセットアップ
`yarn add @prisma/client`


# Userモデルの作成
`nest g module user`
`nest g resolver user --no-spec`  
`nest g service user --no-spec`

# Passwordの暗号化
`yarn add bcrypt`
`yarn add --dev @types/bcrypt`