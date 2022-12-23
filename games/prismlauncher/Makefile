PORTNAME=      PrismLauncher
DISTVERSION=   6.1
CATEGORIES=    games
MASTER_SITES=  https://github.com/PrismLauncher/${PORTNAME}/releases/download/${DISTVERSION}/
DISTFILES=     ${PORTNAME}-${DISTVERSION}.tar.gz

USE_JAVA=       yes
JAVA_VERSION=   17+
USE_QT5=        core gui network widgets
USE_GL=         gl opengl
USES=           cmake
BUILD_DEPENDS=  kf5-extra-cmake-modules>=5.87.0:devel/kf5-extra-cmake-modules \
				qt5-buildtools>=5.15.2:devel/qt5-buildtools \
				qt5-qmake>=5.15.2:devel/qt5-qmake \
				qt5-testlib>0:devel/qt5-testlib \
				zlib-ng>0:archivers/zlib-ng
RUN_DEPENDS=    lwjgl3>0:games/lwjgl3

MAINTAINER=  me@axyria.dev
COMMENT=     A custom launcher for Minecraft forked from MultiMC

.include <bsd.port.mk>
