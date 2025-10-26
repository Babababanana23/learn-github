# learn-github

Saharat
#include <stdio.h>
#include <string.h>

// โครงสร้างข้อมูลผู้ใช้
struct User {
    char username[50];
    char password[50];
};

// ฟังก์ชันตรวจสอบข้อมูลผู้ใช้
int login(struct User users[], int userCount, char *username, char *password) {
    for (int i = 0; i < userCount; i++) {
        if (strcmp(users[i].username, username) == 0 && strcmp(users[i].password, password) == 0) {
            return 1; // ล็อคอินสำเร็จ
        }
    }
    return 0; // ล็อคอินไม่สำเร็จ
}

int main() {
    struct User users[2] = {{"user1", "pass1"}, {"user2", "pass2"}};
    char username[50];
    char password[50];

    printf("Username: ");
    scanf("%s", username);
    printf("Password: ");
    scanf("%s", password);

    if (login(users, 2, username, password)) {
        printf("Login successful!\n");
    } else {
        printf("Login failed!\n");
    }

    return 0;
}
