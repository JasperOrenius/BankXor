# BankXor

## Features
- **Create an Account**: Users can create a new account with a unique name and password.
- **Log In**: Existing users can log in using their account name and password.
- **Deposit and Withdraw Money**: Once logged in, users can deposit and withdraw funds from their account.
- **View Balance**: Users can view their current balance.
- **Persistent Data Storage**: Accounts are stored in a text file (`BankAccounts.txt`), ensuring data persists across sessions.
- **XOR Encryption**: Account information, including passwords, is encrypted using a simple XOR encryption algorithm before being saved to the file.

## How It Works

### 1. Account Creation
Users can create an account by providing a unique account name and a password. The password is stored in an encrypted format using XOR encryption to add a layer of security to the stored data.

### 2. Log In
Users can log in by entering their account name and password. The entered password is encrypted using the same XOR encryption algorithm and then compared with the stored encrypted password. If the passwords match, access to the account is granted.

### 3. Account Management
Once logged in, users can:
- **View Balance**: Displays the current balance of the account.
- **Deposit**: Allows the user to add funds to their account.
- **Withdraw**: Allows the user to withdraw funds from their account, provided they have sufficient balance.

### 4. Data Persistence
All account information, including balances and encrypted passwords, is stored in a text file named `BankAccounts.txt`. This file ensures that account data persists between program executions. 

### 5. XOR Encryption
BankXor uses a basic XOR encryption algorithm to encrypt sensitive data, such as passwords and account information. The XOR cipher works by performing a bitwise XOR operation between the characters of the data and a fixed encryption key. This is a simple yet effective way to obscure the data:
```csharp
public static string EncryptedData(string data)
{
    string encryptedData = "";
    for (int i = 0; i < data.Length; i++)
    {
        encryptedData += (char)(data[i] ^ encryptionKey[i % encryptionKey.Length]);
    }
    return encryptedData;
}
```
## Getting Started

#### Prerequisites
- **.NET Framework 4.8**: Ensure that the .NET Framework 4.8 is installed on your machine. You can download the [Developer Pack](https://dotnet.microsoft.com/download/dotnet-framework/net48) if it's not already installed.
- **Visual Studio 2019** or later: Install Visual Studio with the **.NET desktop development** workload to develop and build .NET Framework applications.

### Clone the Repository

1. Clone the repository to your local machine:

    ```bash
    git clone https://github.com/your-username/BankXor.git
    ```

### Building and Running the Application

1. **Open the Project in Visual Studio**:
    - Navigate to the cloned `BankXor` directory.
    - Open the `BankXor.sln` file with Visual Studio.

2. **Build the Solution**:
    - In Visual Studio, go to the `Build` menu and select `Build Solution`. This will restore any required packages and build the application.

3. **Run the Application**:
    - After the solution is built, go to the `Debug` menu and select `Start Without Debugging` or press `Ctrl + F5`. This will launch the console application.

4. **Interact with the Application**:
    - Once the application is running, follow the on-screen prompts to:
        - **Create an Account**: Set up a new account with a username and password.
        - **Log In**: Access your account using the credentials you created.
        - **Deposit/Withdraw**: Manage your balance by depositing or withdrawing funds.
        - **View Balance**: Check the current balance of your account.

## Configuration
- The application stores account data in a text file named `BankAccounts.txt` located in the same directory as the executable.
- **Encryption Key**: The XOR encryption key used is `"encryptionKey1234"`. You can change this key in the code if needed for additional security.

## Troubleshooting
- If you encounter issues with loading or saving account data, ensure that `BankAccounts.txt` has the correct permissions and is not being used by another process.
- For any errors or unexpected behavior, check the console output for detailed error messages.
