# photoroll

## Shopify Backend Developer Challenge

This project will be a quick Rails-based image uploader. I am focusing on proper auth and the ability to securely upload and delete images to start. 

### Caveat Emptor!

I have included some basic validations and security measures; they are by no means exhaustive. For example: passwords must be present, and they are hashed and securely stored, but I did not include checks on password strength for ease of testing. These can easily be added at a later date. Session management is done via cookies, which is a Rails default behavior. I have configured the production environment to require SSL for cookie transmission, but the development environment uses insecure transmission. Cookies expire upon logout or after 2 days. Routes have been restricted to disallow access to restricted resources via exploiting Rails path conventions. 

### Features

- Login/Signup/Logout
- Photo upload
- Secure image storage and deletion
- Public/private image designation
- File type validation to prevent malicious uploads
- Private images are only viewable by the user who uploaded them.
- Automatic session expiration

### Technologies

- Rails 6
- Active Storage (image storage)
- `file_validators` gem for checking filetypes
- SQLite
- Active Model has_secure_password (Bcrypt for password management)
- Static code analysis via `brakeman` gem
- Additional static code analysis via `dawnscanner` gem

### Environment setup

Clone down the repo -> `cd ./photoroll` -> `rails db:migrate` -> `rails s` -> `localhost:3000` in your favorite browser!

Static analysis reports via brakeman: Run `brakeman` in the root Rails directory. View results in the terminal

Static analysis via dawnscanner: Run `dawn .` in the root Rails directory. Results will appear in a `~/dawnscanner` folder as text files.

### Screenshots

***Please forgive the barebones styling!***

**Homepage**
![Homepage](/screenshots/homepage.png)

**Login**
![Login](/screenshots/login.png)

**Profile View**
![Profile View](screenshots/profile_view.png)

**Other User View**
![Other User View](screenshots/other_user_view.png)

## TODO

- [x] Add columns to Post to allow for public/private viewing
- [x] Implement login/signup
- [x] Create basic routes (login/signup/logout, home, upload, view, delete)
- [x] Create unstyled views
- [x] Properly store images
- [x] Filetype validation (only jpeg, jpg, and png for now)
- [x] Delete images
- [x] Secure image storage
- [x] Session expiration
- [ ] **Styling**
- [ ] Testing via RSpec
- [x] Update readme with installation section
- [x] Add screenshots to readme
- [x] Add error page for routes when not following happy path that does not conflict with ActiveStorage
