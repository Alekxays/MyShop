
# MyShop | Project EDS

MyShop is a project where we had to create an E-Commerce site connected with an API and code in JS view. 


## Installation

To run the project, you need Docker for the back-end part. Here's all the step when you have install Docker and Docker Compose.

1) First, go into "*docker*" folder and run "*docker-compose up -d --build*" to install the environment
2) Now all your 4 containers should be running (it can take up to 1 minute before container are loaded: if you have the symfony default page on http://localhost/ that mean everything has been loaded correctly and you can pursue). Now you can go inside PHP container and follow the next steps.
3) Inside your PHP container, run "*bin/console doctrine:database:create*" (you should see a success message)
4) Then run "*bin/console doctrine:migrations:migrate*" to update your database
5) To use auth system you also run this "*bin/console lexik:jwt:generate-keypair*"
6) Last thing to do is to run "*bin/console app:add-user*" and follow the process to have your first user on the project.

##

To have access to the front-end, you need to do this.

```bash
    cd myshop
    npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```

## Authors

- [@ZadoxYT](https://www.github.com/ZadoxYT)

For educational purposes only. 

