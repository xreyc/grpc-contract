## Implementation steps

#### Clone
```bash
git clone git@github.com:xreyc/grpc-contract.git
cd grpc-contract
```

#### Initialize go module
```bash
go mod init github.com/xreyc/grpc-contract
```

#### Project structure
```
grpc-contract/
└── auth/
    └── v1/
        └── user.proto
```

For future reference

```
grpc-contract/
├── auth/
│   └── v1/
│       └── user.proto
├── billing/
│   └── v1/
│       └── invoice.proto
```

#### Create proto file `user.proto`
`grpc-contract/auth/v1/user.proto`
```proto
syntax = "proto3";

package auth.v1;

option go_package = "github.com/xreyc/grpc-contract/auth/v1;authv1";

service UserService {
  rpc GetUserDetails(GetUserRequest) returns (GetUserResponse);
}

message GetUserRequest {
  string username = 1;
}

message GetUserResponse {
  string username = 1;
  string email = 2;
  string full_name = 3;
}
```

#### Push to repo
```bash
git add .
git commit -m "Initial commit with auth/v1/user.proto"
git push origin main
```