# $FreeBSD$

PORTVERSION=	2.3.3.0
PORTREVISION=	3
PKGNAMESUFFIX=	23

CONFLICTS=	ansible-* \
		ansible1-* \
		ansible24-* \
		ansible25-* \
		ansible26-*

MASTERDIR=	${.CURDIR}/../ansible
DISTINFO_FILE=	${.CURDIR}/distinfo

PLIST_FILES=	man/man1/ansible-console.1.gz \
		man/man1/ansible-doc.1.gz \
		man/man1/ansible-galaxy.1.gz \
		man/man1/ansible-playbook.1.gz \
		man/man1/ansible-pull.1.gz \
		man/man1/ansible-vault.1.gz \
		man/man1/ansible.1.gz

EXTRA_PATCHES=

.include "${MASTERDIR}/Makefile"
