# $FreeBSD$

PORTNAME=	passivedns
DISTVERSION= ${GH_COMMIT}
CATEGORIES=	security
DISTFILES=	gamelinux-passivedns-1.1.3-60-ga6c7e26.tar.gz

MAINTAINER=	shadowbq@gmail.com
COMMENT=	Network sniffer that logs DNS replies for use in passive DNS setups

LICENSE=	GPLv2

LIB_DEPENDS=	libldns.so:${PORTSDIR}/dns/ldns

USE_GITHUB=	yes
GH_ACCOUNT=	gamelinux
GH_PROJECT=	passivedns
GH_TAG=		${GH_COMMIT}
GH_COMMIT=	a6c7e26

SUB_FILES=	pkg-message

USES=		gmake libtool
USE_AUTOTOOLS=	aclocal autoconf autoheader automake
AUTOMAKE_ARGS=	--add-missing

GNU_CONFIGURE=	yes
CONFIGURE_ARGS=	--with-ldns-libraries=${PREFIX}/lib
CONFIGURE_ARGS+= --with-ldns-includes=${PREFIX}/include

USE_RC_SUBR=	passivedns

.include <bsd.port.options.mk>

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/src/passivedns \
		${STAGEDIR}${PREFIX}/bin
	${MKDIR} ${STAGEDIR}/var/log/passivedns

.include <bsd.port.mk>
