# Created by: Michael Johnson <ahze@ahze.net>
# $FreeBSD$

PORTNAME=	Video-OpenQuicktime
PORTVERSION=	1.02
PORTREVISION=	7
CATEGORIES=	multimedia perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Interface to the OpenQuicktime library

DEPRECATED=	Uses obsolete glib12
EXPIRATION_DATE=	2018-12-20

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-Inline>=0:devel/p5-Inline \
		p5-Inline-C>=0.01:devel/p5-Inline-C
LIB_DEPENDS=	libopenquicktime.so:multimedia/openquicktime

MAKE_JOBS_UNSAFE=	yes

USES=		perl5
USE_PERL5=	configure

.include <bsd.port.mk>
