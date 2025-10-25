Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser

& C:\HAKIM\etl_project\venv\Scripts\Activate.ps1

& C:\Hakim\Project\peretl\etl_project\venv\Scripts\Activate.ps1

.\etl_project\.venv\Scripts\Activate.ps1

git config --global user.name "Jauhar Hakim"
git config --global user.email hakimmuhammad21@gmail.com




=================================
python3 -m venv .venv

source .venv/bin/activate

python -m pip install -r requirements.txt

export AIRFLOW_HOME=~/airflow

AIRFLOW_VERSION=3.0.6

PYTHON_VERSION="$(python --version | cut -d " " -f 2 | cut -d "." -f 1-2)"

CONSTRAINT_URL="https://raw.githubusercontent.com/apache/airflow/constraints-${AIRFLOW_VERSION}/constraints-${PYTHON_VERSION}.txt"

pip install "apache-airflow==${AIRFLOW_VERSION}" --constraint "${CONSTRAINT_URL}"


airflow db init

airflow users create \
    --username admin \
    --firstname jauhar \
    --lastname hakim \
    --role Admin \
    --email mikikkikim0@gmail.com
password : hakim123
Simple auth manager | Password for user 'admin': 7MG833FXHqTqaGU7

airflow webserver --port 8080
airflow api-server --port 8080

airflow scheduler



export DBT_THREADS=1
export OMP_NUM_THREADS=1

sudo update-alternatives --config python3

dbt run --threads 2

