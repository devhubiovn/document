# Library devhub maven
## com.app.pulgins.Auth Class

### Giới Thiệu
`Auth` là một class Java được sử dụng để quản lý xác thực và quyền truy cập trong ứng dụng. Nó chứa các phương thức để kiểm tra xem một người dùng có quyền truy cập vào một tài nguyên cụ thể hay không.

### Hướng Dẫn Sử Dụng
1. **Khởi Tạo Auth**: Bạn có thể khởi tạo một đối tượng `Auth` và thiết lập các vai trò và chức năng mặc định bằng cách sử dụng constructor của nó:
    ```java
    Auth auth = new Auth();
    ```
2. **Thêm URL**: Sử dụng phương thức `addUrl(String url)` để thêm một URL vào danh sách chức năng:
    ```java
    auth.addUrl("example/role");
    ```
3. **Thêm Tên Chức Năng**: Sử dụng phương thức `addFunctionName(String function_name)` để thêm tên chức năng vào danh sách:
    ```java
    auth.addFunctionName("addRoleFunction");
    ```
4. **Thêm Vai Trò Chức Năng**: Sử dụng phương thức `addRoleFunction(String role_function)` để thêm vai trò chức năng vào danh sách:
    ```java
    auth.addRoleFunction("admin");
    ```
5. **Thêm Hành Động Cho Phép**: Sử dụng phương thức `addActionAllow(String action)` để thêm hành động cho phép vào danh sách:
    ```java
    auth.addActionAllow("create");
    ```
6. **Kiểm Tra Quyền Truy Cập**: Sử dụng phương thức `hasPermissionPrivateBean(User user, String url, String function_name, String action)` hoặc `hasPermissionPublicBean(User user, String url, String function_name, String action)` để kiểm tra quyền truy cập của người dùng:
    ```java
    User user = new User("admin");
    boolean hasPermission = auth.hasPermissionPrivateBean(user, "example/role", "addRoleFunction", "create");
    ```
    Hoặc:
    ```java
    boolean hasPermission = auth.hasPermissionPublicBean(user, "example/role", "addRoleFunction", "create");
    ```

### Class User
`User` là một class nested trong `Auth`, mô tả người dùng trong hệ thống.

1. **Khởi Tạo User**: Bạn có thể khởi tạo một đối tượng `User` bằng cách truyền tên người dùng vào constructor của nó:
    ```java
    User user = new User("admin");
    ```
2. **Lấy Tên Người Dùng**: Sử dụng phương thức `getUsername()` để lấy tên người dùng:
    ```java
    String username = user.getUsername();
    ```
3. **Lấy Danh Sách Vai Trò**: Sử dụng phương thức `getRoles()` để lấy danh sách vai trò của người dùng:
    ```java
    Set<String> roles = user.getRoles();
    ```

