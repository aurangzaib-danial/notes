
# Rails Credentials

This is Rails equivalent of environment variables. All secrets related to a application are saved in an encrypted file located at `config/credentials.yml.enc'. The key for this encrypted file is located in `config/master.key`.

- Rails credentials feature allows us to keep us organized.
- We can track the encrypted file in our git repo and decrypt it inside the production environment. This way we do not have to define all environment variables inside production environment.


## master.key

- Generated with a new Rails app.
- The key inside this file encrypts our credentials.
- Must never track in git.
- In production credentials are automatically included if **RAILS\_MASTER\_KEY** ENV variable is defined.

## Editing Credentials

These can only be edited if the master key is present in the config folder.

```shell
  EDITOR='sublime --wait' rails credentials:edit
```

On closing the file after making a change, rails encrypts it again.

### credentials.yml

This a yaml file. We can make groups for development and production but we have to manually access each environment keys. Rails does not automatically include keys based on environments.

```yaml
  development:
    facebook:
      app_id: 123
      secret: 123

  production:
    google:
      app_id: 123
      secret: 123
```


## Accessing Credentials

```ruby
  credentials = Rails.application.credentials[Rails.env.to_sym]

  facebook = credentials[:facebook]

  facebook[:app_id]

  facebook[:secret]
```
