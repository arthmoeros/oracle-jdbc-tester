# oracle-jdbc-tester

A simple command line application to test JDBC connection to Oracle Database.

## How to run

Clone this repository and then run:

```sh
mvn clean package
```

Or download the JAR file from [release](https://github.com/aimtiaz11/jdbc-tester/releases) page.

Execute the JAR file with the following 2 parameters JDBC connection details and optional query, authentication credentials must be set as environment variables:

```sh
env ORACLEDB_USER=myuser ORACLEDB_PASS=mypass java -jar target/jdbc-tester-1.0.jar jdbc:oracle:thin:@//<host>:<port>/<SID> [optional_query]
```

## How it works

The application connects to the Oracle database and executes a single SQL query: `select sysdate from dual` or provided query, and prints the output.

If it cannot connect for whatever reason, it will fail by logging an error message.

There is a default connection timeout set to 8 seconds, it can be changed via the environment variable `ORACLEDB_CONNTIMEOUT`.
Also, there is a max rows printed out from the ResultSet, default is 10 rows, it can be changed via the environment variable `RESULTSET_MAX_ROWS`.

## License

(The MIT License)

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
