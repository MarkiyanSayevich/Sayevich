.DEFAULT_GOAL := all

all: install test run deploy

install:
	@echo "Installing pipenv and dependencies."
	@pip install pipenv
	@pipenv install requests ntplib pytest
test:
	@echo "Start tests."
	@pipenv run pytest tests/tests.py | tee results.txt
run:
	@echo "Run Python app."
	@pipenv run python app.py | tee -a results.txt
deploy:
	@echo "Adding and Committing results.txt to git."
	@git add results.txt \
	&& git commit -m "lab_2: Make - results.txt"\
	&& git push
