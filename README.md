# fly.io deployment

<img src="https://i.imgur.com/98fJcc7.jpg">

## To set up and deploy your project, follow the steps below:

1. **Sign up for a fly.io Account**

   Visit [fly.io](https://fly.io) and sign up for an account. Enter your credit card information (you will not be charged).

2. **Install the fly.io CLI Tool**

   Install the fly.io CLI tool by running the following command in your terminal:

   ```bash
   curl -L https://fly.io/install.sh | sh
   ```
   
3. **Open your zshrc File**

   After installing the CLI, you should see an output that recommends adding two lines to your `.zshrc` file. They will look similar to this:

   ```sh
   export FLYCTL_INSTALL="/Users/<your_username>/.fly"
   export PATH="$FLYCTL_INSTALL/bin:$PATH"
   ```

   Copy these two lines.
   
   Open your `.zshrc` file by entering the following command in your terminal:

   ```bash 
   open ~/.zshrc
   ```

   Then paste the two lines at the bottom of this file and save.

5. **Login to your fly.io account** 

   Authenticate your fly.io account through the command line:

   ```bash
   flyctl auth login
   ```

6. **Launch your server**

   Navigate to the directory where your `server.js` is located and run the following command:

   ```bash
   flyctl launch
   ```

   WHen prompted to type `Y/N` to adjust settings, type `Y` and the fly.io dashboard should open up in your browser. Adjust these settings as you like, particularly your app name, as that is what will be your fly.io URL.
   
7.  **Set secrets(environment variables) for your project**
   
   Set the necessary secrets for your application using the following command format:

   ```bash
   flyctl secrets set <SECRET KEY>=<your secret key>
   ```

   Example:

  ```bash
   flyctl secrets set DATABASE_URL=mongodb+srv://<yourusername>:<yourpassword>@cluster0.bvo1sdn.mongodb.net/mongoose-movies?retryWrites=true&w=majority
   flyctl secrets set GOOGLE_CLIENT_ID=232108574874-st09fal7v3039am9nresglkv9sa6mb3b.apps.googleusercontent.com
   flyctl secrets set GOOGLE_SECRET=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
   flyctl secrets set GOOGLE_CALLBACK=https://<yourdomainname>.fly.dev/oauth2callback
   flyctl secrets set SECRET=samboosaforlunch
  ```

7.  **Deploy the App**

   Deploy your application using the following command:

   ```bash
   flyctl deploy
   ```

8. **Update Google Cloud Console Credentials**

     **Visit Google Cloud Console Credentials Page:**
     - Go to [Google Cloud Console Credentials Page](https://console.cloud.google.com/apis/credentials)

     **Add Authorized Redirect URI:**
     - Add the following URI as an authorized redirect URI:
       - `https://<yourdomainname>.fly.dev/oauth2callback`


[Now your application is set up and deployed on fly.io!](https://www.youtube.com/watch?v=6zT4Y-QNdto)







