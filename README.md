# Solid Queue Testing

This is a minimal Rails, created with Rails 8.0.2 and Ruby 3.4.2, to reproduce the behavior in [Solid Queue issue #512](https://github.com/rails/solid_queue/issues/512).

This uses Postgres, with Solid Queue in a separate database, and running inside Puma.

To reproduce:
  * set up and start the app: `bin/setup`
  * stop the Postgres server
  * puma should exit with a crash, along with a message: `Detected Solid Queue has gone away...`

When running `bin/jobs` separately without the server, it should also crash when Postgres is stopped
