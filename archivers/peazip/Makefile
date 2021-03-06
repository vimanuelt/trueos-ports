# $FreeBSD$

PORTNAME=	peazip
PORTVERSION=	6.6.1
CATEGORIES=	archivers
PKGNAMESUFFIX=	${LAZARUS_PKGNAMESUFFIX}
MASTER_SITES=	https://github.com/giorgiotani/PeaZip/releases/download/${PORTVERSION}/
DISTNAME=	${PORTNAME}-${PORTVERSION}.src

MAINTAINER=	acm@FreeBSD.org
COMMENT=	Free archiver and file compressor

LICENSE=	LGPL3

USES=		dos2unix fpc lazarus:flavors zip
USE_FPC=	cairo chm fcl-base fcl-image pasjpeg rtl-objpas x11
USE_XORG=	x11

SUB_FILES=	pea pealauncher peazip

DOS2UNIX_REGEX=		.*\.([txt]|pas|lpi|txt)

LAZARUS_PROJECT_FILES=	project_pea.lpi project_peach.lpi project_gwrap.lpi
LAZBUILD_ARGS=		-d

gtk2_CONFLICTS_INSTALL=	${PORTNAME}-qt4 ${PORTNAME}-qt5
qt4_CONFLICTS_INSTALL=	${PORTNAME}-gtk2 ${PORTNAME}-qt5
qt5_CONFLICTS_INSTALL=	${PORTNAME}-gtk2 ${PORTNAME}-qt4

ARCHIVER_FILES=		#

OPTIONS_DEFINE=		7Z ARC ZPAQ UNACE

7Z_DESC=		7z file archiver support
ARC_DESC=		Arc file archiver support
ZPAQ_DESC=		Zpaq file archiver support
UNACE_DESC=		Unace file archiver support

OPTIONS_DEFAULT=	7Z

.if ${FLAVOR:Ugtk2:Mgtk2}
USE_GNOME+=	cairo
.endif

.include <bsd.port.options.mk>

.if ${PORT_OPTIONS:M7Z}
RUN_DEPENDS+=	7z:archivers/p7zip
ARCHIVER_FILES+=7z
PLIST_SUB+=	7Z=""
.else
PLIST_SUB+=	7Z="@comment "
.endif

.if ${PORT_OPTIONS:MARC}
RUN_DEPENDS+=	arc:archivers/arc
ARCHIVER_FILES+=arc
PLIST_SUB+=	ARC=""
.else
PLIST_SUB+=	ARC="@comment "
.endif

.if ${PORT_OPTIONS:MZPAQ}
RUN_DEPENDS+=	zpaq:archivers/paq
ARCHIVER_FILES+=zpaq
PLIST_SUB+=	ZPAQ=""
.else
PLIST_SUB+=	ZPAQ="@comment "
.endif

.if ${PORT_OPTIONS:MUNACE}
RUN_DEPENDS+=	unace:archivers/unace
ARCHIVER_FILES+=unace
PLIST_SUB+=	UNACE=""
.else
PLIST_SUB+=	UNACE="@comment "
.endif

post-patch:
	${REINPLACE_CMD} 's|GetSelectedNodePath|Path|g' ${WRKSRC}/peach.pas

pre-install:
	@${ECHO_CMD} "#" > ${WRKSRC}/altconf.txt
	@${ECHO_CMD} "appdata" >> ${WRKSRC}/altconf.txt

do-install:
	@${MKDIR} ${STAGEDIR}${DATADIR}/res
.for ARCHIVER in ${ARCHIVER_FILES}
	@${MKDIR} ${STAGEDIR}${DATADIR}/res/${ARCHIVER}
	@${LN} -s ${LOCALBASE}/bin/${ARCHIVER} ${STAGEDIR}${DATADIR}/res/${ARCHIVER}/${ARCHIVER}
.endfor
	@cd ${WRKSRC}/res && ${COPYTREE_SHARE} "icons lang themes" ${STAGEDIR}${DATADIR}/res
	@cd ${WRKSRC} && ${INSTALL_DATA} altconf.txt ${STAGEDIR}${DATADIR}/res && \
			${INSTALL_PROGRAM} pea pealauncher ${STAGEDIR}${DATADIR}/res && \
			${INSTALL_PROGRAM} peazip ${STAGEDIR}${DATADIR}
	@cd ${WRKSRC}/FreeDesktop_integration && \
		${INSTALL_DATA} peazip.desktop ${STAGEDIR}${DESKTOPDIR} && \
		${INSTALL_DATA} peazip.png ${STAGEDIR}${PREFIX}/share/pixmaps/
	${INSTALL_SCRIPT} ${WRKDIR}/pea ${WRKDIR}/pealauncher ${WRKDIR}/peazip ${STAGEDIR}${PREFIX}/bin/

.include <bsd.port.mk>
