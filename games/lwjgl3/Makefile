# $FreeBSD$
# Original work by Cameron Katri <me@cameronkatri.com>

PORTNAME=       	lwjgl3
DISTVERSION=    	3.2.2
DISTVERSIONSUFFIX=	-full
CATEGORIES=	        games java
MASTER_SITES=    	https://github.com/CRKatri/lwjgl3/releases/download/${DISTVERSION}-freebsd-3/
LICENSE=        	BSD3CLAUSE

BUILD_DEPENDS=	${LOCALBASE}/lib/libdyncall_s.a:devel/dyncall
LIB_DEPENDS=	libglfw.so:graphics/glfw \
				libopenal.so:audio/openal-soft \
				libopus.so:audio/opus \
				libOpenCL.so:devel/ocl-icd

USES=		gl gnome xorg pkgconfig
USE_ANT=	yes
USE_GL=  	gl egl glesv2
USE_GNOME=	gtk30 glib20
USE_JAVA=	yes
USE_XORG=	x11

MAKE_ENV+=	 LWJGL_BUILD_OFFLINE=true
ALL_TARGET=  all release

MAINTAINER=	me@axyria.dev
COMMENT=    Lightweight Java Game Library 3

do-install:
	@${MKDIR} ${STAGEDIR}${JAVAJARDIR}/${PORTNAME}
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/${PORTNAME}
.for x in ${WRKSRC}/bin/RELEASE/lwjgl*/*.jar
	${INSTALL_DATA} ${WRKSRC}${x} ${STAGEDIR}${JAVAJARDIR}/${PORTNAME}/
.endfor
.for x in ${WRKSRC}/bin/RELEASE/lwjgl*/*license.txt
	${INSTALL_DATA} ${WRKSRC}${x} ${STAGEDIR}${JAVAJARDIR}/${PORTNAME}/
.endfor
.for x in ${WRKSRC}/bin/libs/*.so
	${INSTALL_LIB} ${WRKSRC}${x} ${STAGEDIR}${PREFIX}/lib/${PORTNAME}/
.endfor
	${CP} ${FILESDIR}/wrapper ${STAGEDIR}${PREFIX}/bin/lwjgl3-wrapper
	${CHMOD} 775 ${STAGEDIR}${PREFIX}/bin/lwjgl3-wrapper

.include <bsd.port.mk>
