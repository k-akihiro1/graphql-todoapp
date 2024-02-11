# vscode拡張機能
- GraphQL: Language Feature Support
- GraphQL: Syntax Highlighting
- Prisma
- React Extension Pack

# 環境構築
yarn global add @nestjs/cli
nest new backend :yarn
yarn run start

cd backend
#配下に以下のリポジトリーを配置する
https://github.com/k-akihiro1/graphql-todoapp-backend

yarn add @nestjs/graphql @nestjs/apollo apollo-server-express graphql

yarn add @apollo/server
# バリデーション: https://github.com/typestack/class-validator#validation-decorators
yarn add class-transformer class-validator

# モジュールの作成
nest g module task

# サービスとリゾルバーの設定
nest g resolver task --no-spec
nest g service task --no-spec

# 実行コマンド
yarn start:dev

# 略語
dto: Data Transfer Object

参考文献：
https://docs.nestjs.com/graphql/quick-start#installation
https://zenn.dev/waddy/books/graphql-nestjs-nextjs-bootcamp/viewer/nestjs



リクエストテンプレート
'''
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
'''

'''
{    
  "createTaskInput": {
  	"name":  "test",
    "dueDate": "2024-01-01"
  }
}
'''