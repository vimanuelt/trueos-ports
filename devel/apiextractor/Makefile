# Created by: Nicola Vitale <nivit@FreeBSD.org>
# $FreeBSD$

PORTNAME=	apiextractor
PORTVERSION=	0.10.10
PORTREVISION=	3
CATEGORIES=	devel

MAINTAINER=	wg@FreeBSD.org
COMMENT=	API Extractor library to build PySide

LICENSE=	GPLv2

DEPRECATED=		Qt4 has been EOL since december 2015
EXPIRATION_DATE=	2019-03-15

BUILD_DEPENDS=	sphinx-build:textproc/py-sphinx

USE_GITHUB=	yes
GH_ACCOUNT=	PySide
GH_PROJECT=	Apiextractor

USES=		cmake qt:4
USE_GNOME=	libxml2 libxslt
USE_QT=		gui moc_build qmake_build qtestlib_build \
		rcc_build uic_build xml xmlpatterns
USE_LDCONFIG=	yes

PLIST_SUB=	PORTVERSION=${PORTVERSION}

.include <bsd.port.mk>
