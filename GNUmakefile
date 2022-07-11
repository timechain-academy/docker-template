SHELL := /bin/bash

PWD                                    ?= pwd_unknown

THIS_FILE                              := $(lastword $(MAKEFILE_LIST))
export THIS_FILE
TIME                                   := $(shell date +%s)
export TIME

#GIT CONFIG
GIT_USER_NAME                          := $(shell git config user.name)
export GIT_USER_NAME
GIT_USER_EMAIL                         := $(shell git config user.email)
export GIT_USER_EMAIL
GIT_SERVER                             := https://github.com
export GIT_SERVER
GIT_PROFILE                            := RandyMcMillan
export GIT_PROFILE
GIT_BRANCH                             := $(shell git rev-parse --abbrev-ref HEAD)
export GIT_BRANCH
GIT_HASH                               := $(shell git rev-parse HEAD)
export GIT_HASH
GIT_REPO_ORIGIN                        := $(shell git remote get-url origin)
export GIT_REPO_ORIGIN
GIT_REPO_NAME                          := $(PROJECT_NAME)
export GIT_REPO_NAME
GIT_REPO_PATH                          := $(HOME)/$(GIT_REPO_NAME)
export GIT_REPO_PATH
###      make  report: nocache=true
ifeq ($(nocache),true)
NOCACHE                                := --no-cache
else
NOCACHE                                :=	
endif
export NOCACHE
###      make  report: verbose=true
ifeq ($(verbose),true)
VERBOSE                                := --verbose
else
VERBOSE                                :=	
endif
export VERBOSE

ifeq ($(tag),)
TAG                                    :=$(TIME)
else
TAG                                    :=$(tag)
endif

.PHONY:-
-:help
##      make  help: prints this help message
.PHONY: help
help:
	@echo "Usage: make [arg]"
	@echo ''
	@sed -n 's/^## //p' ${MAKEFILE_LIST} | column -t -s ':' |  sed -e 's/^/ /'
	@echo ''
	@echo 'Examples:'
	@echo ''
	@sed -n 's/^### //p' ${MAKEFILE_LIST} | column -t -s ':' |  sed -e 's/^/ /'
	@echo ''
##      make  report: print git/system variable
.PHONY: report
report:
	@echo ''
	@echo '      args:'
	@echo '        - THIS_FILE=${THIS_FILE}'
	@echo '        - TIME=${TIME}'
	@echo '        - HOME=${HOME}'
	@echo '        - PWD=${PWD}'
	@echo '        - TAG=${TAG}'
	@echo '        - GIT_USER_NAME=${GIT_USER_NAME}'
	@echo '        - GIT_USER_EMAIL=${GIT_USER_EMAIL}'
	@echo '        - GIT_SERVER=${GIT_SERVER}'
	@echo '        - GIT_PROFILE=${GIT_PROFILE}'
	@echo '        - GIT_BRANCH=${GIT_BRANCH}'
	@echo '        - GIT_HASH=${GIT_HASH}'
	@echo '        - GIT_REPO_ORIGIN=${GIT_REPO_ORIGIN}'
	@echo '        - GIT_REPO_PATH=${GIT_REPO_PATH}'
	@echo '        - NOCACHE=${NOCACHE}'
	@echo '        - VERBOSE=${VERBOSE}'
	@echo ''
