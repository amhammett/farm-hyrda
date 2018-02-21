
env := missing
account := dev
region := us-west-2

ansible_cmd = AWS_PROFILE=$(account) AWS_DEFAULT_REGION=$(region) ./venv/bin/ansible-playbook
farm_vars = -e env=$(env) -e account=$(account) $(debug)

venv:
	virtualenv venv

install: | venv
	./venv/bin/pip install -r requirements.txt

deploy:
	$(ansible_cmd) deploy.yml $(farm_vars)

terminate:
	$(ansible_cmd) terminate.yml $(farm_vars)

test:
	ansible --version
