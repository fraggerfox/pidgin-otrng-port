# $FreeBSD$

PORTNAME=	pidgin-otrng
PORTVERSION=	0.0.0
CATEGORIES=	security net-im net
MASTER_SITES=	https://otr.im/

MAINTAINER=	santhosh.raju@gmail.com
COMMENT=	Allows deniable private conversations using Pidgin with \
		OTR version 4

LICENSE=	GPLv2
LICENSE_FILE=	${WRKSRC}/COPYING

BUILD_DEPENDS=	pidgin:net-im/pidgin
LIB_DEPENDS=	libgcrypt.so:security/libgcrypt \
		libgpg-error.so:security/libgpg-error \
		libgoldilocks.so:security/libgoldilocks \
		libotr.so:security/libotr \
		libotr-ng.so:security/libotr-ng \
		libpurple.so:net-im/libpurple \
		libsodium.so:security/libsodium

USES=		autoreconf cpe gmake libtool pkgconfig gnome
USE_GNOME=	gtk20 intltool

CPE_VENDOR=	otrv4
CPE_PRODUCT=	${PORTNAME}

GNU_CONFIGURE=	yes

USE_GITHUB=	yes
GH_ACCOUNT=	otrv4
GH_PROJECT=	pidgin-otrng
GH_TAGNAME=	701e8e4

INSTALL_TARGET=	install-strip

# This is needed for libotr to be detected correctly
CPPFLAGS+=	-I${LOCALBASE}/include
LDFLAGS+=	-L${LOCALBASE}/lib
CONFIGURE_ARGS=	--with-libotr-prefix=${LOCALBASE}/lib \
		--with-libotr-inc-prefix=${LOCALBASE}/include

OPTIONS_DEFINE=	NLS
OPTIONS_SUB=	yes

NLS_USES=	gettext
NLS_USES_OFF=	gettext-tools

.include <bsd.port.mk>
