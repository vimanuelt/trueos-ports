# $FreeBSD$

PORTNAME=	connectivity
DISTVERSION=	${QT5_VERSION}
PORTREVISION=	1
CATEGORIES=	comms
PKGNAMEPREFIX=	qt5-

MAINTAINER=	kde@FreeBSD.org
COMMENT=	Qt connectivity (Bluetooth/NFC) module

USE_QT=		concurrent core declarative buildtools_build
USES=		compiler:c++11-lang qmake qt-dist:5,connectivity

USE_LDCONFIG=	${PREFIX}/${QT_LIBDIR_REL}

.include <bsd.port.mk>
