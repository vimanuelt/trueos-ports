# Created by: Thorsten Greiner <thorsten.greiner@web.de>
# $FreeBSD$

PORTNAME=	xfce4-systemload-plugin
PORTVERSION=	1.2.2
CATEGORIES=	sysutils xfce
MASTER_SITES=	XFCE/src/panel-plugins/${PORTNAME}/${PORTVERSION:R}
DIST_SUBDIR=	xfce4

MAINTAINER=	xfce@FreeBSD.org
COMMENT=	System Load plugin for Xfce4 panel

LICENSE=	BSD2CLAUSE

USES=		gettext-tools gmake libtool pkgconfig tar:bzip2 xfce:gtk3
USE_GNOME=	gtk30 intltool cairo gdkpixbuf2
USE_XFCE=	panel

SSP_UNSAFE=	yes
GNU_CONFIGURE=	yes
INSTALL_TARGET=	install-strip

OPTIONS_DEFINE= NLS UPOWER
OPTIONS_DEFAULT=UPOWER
UPOWER_DESC=	Use upower for adapting update interval to power state
OPTIONS_SUB=	yes

NLS_CONFIGURE_ENABLE=	nls
NLS_USES=	gettext-runtime

UPOWER_CONFIGURE_ENABLE=upower
UPOWER_LIB_DEPENDS=	libupower-glib.so:sysutils/upower

.include <bsd.port.mk>
