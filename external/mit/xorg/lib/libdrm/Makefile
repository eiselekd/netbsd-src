#	$NetBSD: Makefile,v 1.14 2016/08/20 20:19:08 joerg Exp $

.include <bsd.own.mk>

LIB=	drm
.PATH:	${X11SRCDIR.${LIB}}

SRCS=	xf86drm.c xf86drmHash.c xf86drmMode.c xf86drmRandom.c xf86drmSL.c

INCS=	xf86drm.h xf86drmMode.h
INCSDIR=${X11INCDIR}

CPPFLAGS+=	-I${DESTDIR}${X11INCDIR}/libdrm

SUBDIR=	drm kms

PKGCONFIG=	libdrm
PKGDIST=	${LIB}

COPTS.xf86drm.c+=	${${ACTIVE_CC} == "gcc":? -Wno-error=cpp :}
COPTS.xf86drm.c+=	${${ACTIVE_CC} == "clang":? -Wno-error=\#warnings :}

CWARNFLAGS.clang+=	-Wno-conversion -Wno-tautological-compare

LIBDPLIBS=	m	${.CURDIR}/../../../../../lib/libm

.if 0
MAN=		drm.7 \
		drm-kms.7 \
		drm-memory.7 \
		drmAvailable.3 \
		drmHandleEvent.3 \
		drmModeGetResources.3
# XXX is this right?
MLINKS+=	drm-mm.7 drm-gem.7 \
		drm-mm.7 drm-ttm.7
.endif

.include "Makefile.defines"

.include <bsd.x11.mk>
.include <bsd.lib.mk>
.include <bsd.subdir.mk>
