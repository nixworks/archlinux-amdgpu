# Author: Janusz Lewandowski <lew21@xtreeme.org>
# Maintainer: David McFarland <corngood@gmail.com>
# Autogenerated from AMD's Packages file

pkgbase=amdgpu-pro-installer
pkgname=(amdgpu-pro amdgpu-pro-dkms amdgpu-pro-libdrm amdgpu-pro-libgl amdgpu-pro-opencl amdgpu-pro-vdpau amdgpu-pro-vulkan lib32-amdgpu-pro lib32-amdgpu-pro-libdrm lib32-amdgpu-pro-libgl lib32-amdgpu-pro-opencl lib32-amdgpu-pro-vdpau lib32-amdgpu-pro-vulkan xf86-video-amdgpu-pro)
pkgver=16.60.379184
pkgrel=0
arch=('x86_64')
url='http://www.amd.com'
license=('custom:AMD')
makedepends=('wget')

DLAGENTS='https::/usr/bin/wget --referer https://support.amd.com/en-us/kb-articles/Pages/AMDGPU-PRO-Install.aspx -N %u'

source=(https://www2.ati.com/drivers/linux/ubuntu/amdgpu-pro-16.60-379184.tar.xz
	0001-add-archlinux-as-build-option.patch
	0002-fix_get_user_pages_calls.patch
	0003-fix_drm_connector.patch
	0004-Change-seq_printf-format-for-64-bit-context.patch
	0005-fix_drm_vma_node_verify_access.patch
	0006-fix_dm_plane_helper_funcs.patch)
sha256sums=(d88b5a747ac765a75eb738aaf5641428c3b1c9c02bc6fde452c423de7dd620bd
	400df0077464003fad74bb77a8f6e5ba24bffc7c2e32e6b3f0dab08a17eb3486
	5708b6641bd62fe768e1cb36f88d0895c4fdf90d1d3110033bafdabc47fe1e31
	b6a98ed84733bab544461991f642dc1a73ee065b32f7c1b3a235d5e2bc814943
	21c78811107d8ee59f3566d21ed4a7ccfd622f4e07350fca7ed662392ab07190
	f743cd2205645cf10640d4d2f781b6b158b3d9f0ed15666b3f9bc7fc082be4a8
	b10bb6b2382f995ee90f9cc807b69cb336d0edb65096b66df315f0c60132e04d)

PKGEXT=".pkg.tar"


# extracts a debian package
# $1: deb file to extract
extract_deb() {
	local tmpdir="$(basename "${1%.deb}")"
	rm -Rf "$tmpdir"
	mkdir "$tmpdir"
	cd "$tmpdir"
	ar x "$1"
	tar -C "${pkgdir}" -xf data.tar.xz
}
# move ubuntu specific /usr/lib/x86_64-linux-gnu to /usr/lib
# $1: library dir
# $2: destination (optional)
move_libdir() {
	local libdir="usr/lib"
	if [ -n "$2" ]; then
		libdir="$2"
	fi
	if [ -d "$1" ]; then
		if [ -d "${pkgdir}/${libdir}" ]; then
			cp -ar -t "${pkgdir}/${libdir}/" "$1"/*
			rm -rf "$1"
		else
			mkdir -p "${pkgdir}/${libdir}"
			mv -t "${pkgdir}/${libdir}/" "$1"/*
			rmdir "$1"
		fi
	fi
}


package_amdgpu-pro () {
	pkgdesc="The AMDGPU Pro driver package"
	install=amdgpu-pro-core.install
	arch=('x86_64')
	depends=('glib2>=2.37.3' 'gst-plugins-base>=1.6.0' 'gstreamer>=1.0.0' 'lib32-amdgpu-pro-libdrm=16.60.379184-0' 'lib32-amdgpu-pro-opencl=16.60.379184-0' 'lib32-amdgpu-pro-vdpau=16.60.379184-0' 'lib32-amdgpu-pro-vulkan=16.60.379184-0' 'lib32-amdgpu-pro=16.60.379184-0' 'libomxil-bellagio' 'libx11' 'libx11>=1.4.99.1' 'libxcb' 'libxcb>=1.8' 'libxcb>=1.9.2' 'libxdamage>=1.1' 'libxext' 'libxfixes' 'libxshmfence' 'libxxf86vm' 'ncurses>=6' 'openssl>=1.0.0' 'xf86-video-amdgpu-pro=16.60.379184-0' 'zlib>=1.2.0')

	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./amdgpu-pro_16.60-379184_amd64.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./amdgpu-pro-lib32_16.60-379184_amd64.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./gst-omx-amdgpu-pro_1.0.0.1-379184_amd64.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libegl1-amdgpu-pro_16.60-379184_amd64.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libgbm1-amdgpu-pro_16.60-379184_amd64.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libgbm1-amdgpu-pro-base_16.60-379184_all.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libgbm1-amdgpu-pro-dev_16.60-379184_amd64.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libgl1-amdgpu-pro-appprofiles_16.60-379184_all.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libgl1-amdgpu-pro-dri_16.60-379184_amd64.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libgl1-amdgpu-pro-ext_16.60-379184_amd64.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libgl1-amdgpu-pro-glx_16.60-379184_amd64.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libglamor-amdgpu-pro-dev_1.18.3-379184_amd64.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libgles2-amdgpu-pro_16.60-379184_amd64.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./mesa-amdgpu-pro-omx-drivers_12.0.3-379184_amd64.deb
	#move_libdir "${pkgdir}/opt/amdgpu-pro" "usr"
	#move_libdir "${pkgdir}/opt/amdgpu-pro/lib/x86_64-linux-gnu"
	move_libdir "${pkgdir}/lib"

	# extra_commands:
	mv "${pkgdir}"/usr/lib/x86_64-linux-gnu/dri ${pkgdir}/usr/lib/
	# This is needed because libglx.so has a hardcoded DRI_DRIVER_PATH
	ln -s /usr/lib/dri ${pkgdir}/usr/lib/x86_64-linux-gnu/dri
	#mkdir -p ${pkgdir}/etc/ld.so.conf.d/
	#ln -s /usr/lib/amdgpu-pro/ld.conf ${pkgdir}/etc/ld.so.conf.d/10-amdgpu-pro.conf
	#mkdir -p ${pkgdir}/etc/modprobe.d/
	#ln -s /usr/lib/amdgpu-pro/modprobe.conf ${pkgdir}/etc/modprobe.d/amdgpu-pro.conf
	#mkdir -p "${pkgdir}"/usr/lib/amdgpu-pro
	#mv "${pkgdir}"/usr/lib/libGLESv2.so* "${pkgdir}"/usr/lib/amdgpu-pro/
	#mv "${pkgdir}"/usr/lib/libGL.so* "${pkgdir}"/usr/lib/amdgpu-pro/
	#mv "${pkgdir}"/usr/lib/libEGL.so* "${pkgdir}"/usr/lib/amdgpu-pro/
}


package_amdgpu-pro-dkms () {
	pkgdesc="amdgpu-pro driver in DKMS format."
	arch=('any')
	depends=('dkms>=1.95')

	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./amdgpu-pro-dkms_16.60-379184_all.deb
	#move_libdir "${pkgdir}/opt/amdgpu-pro" "usr"
	#move_libdir "${pkgdir}/opt/amdgpu-pro/lib/x86_64-linux-gnu"
	move_libdir "${pkgdir}/lib"

	# extra_commands:
	msg 'Applying patches...'
	(cd ${pkgdir}/usr/src/amdgpu-pro-16.60-379184;
		sed -i 's/\/extra/\/extramodules/' dkms.conf
			msg2 '0001-add-archlinux-as-build-option.patch'
		patch -p1 -i "${srcdir}/0001-add-archlinux-as-build-option.patch";
		msg2 '0002-fix_get_user_pages_calls.patch'
		patch -p1 -i "${srcdir}/0002-fix_get_user_pages_calls.patch";
		msg2 '0003-fix_drm_connector.patch'
		patch -p1 -i "${srcdir}/0003-fix_drm_connector.patch";
		msg2 '0004-Change-seq_printf-format-for-64-bit-context.patch'
		patch -p1 -i "${srcdir}/0004-Change-seq_printf-format-for-64-bit-context.patch";
		msg2 '0005-fix_drm_vma_node_verify_access.patch'
		patch -p1 -i "${srcdir}/0005-fix_drm_vma_node_verify_access.patch";
		msg2 '0006-fix_dm_plane_helper_funcs.patch'
		patch -p1 -i "${srcdir}/0006-fix_dm_plane_helper_funcs.patch"
	)
}


package_amdgpu-pro-libdrm () {
	pkgdesc="The AMDGPU Pro userspace interface to kernel DRM services"
	arch=('x86_64')
	depends=('bcunit')

	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libdrm-amdgpu-pro-amdgpu1_2.4.70-379184_amd64.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libdrm-amdgpu-pro-dev_2.4.70-379184_amd64.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libdrm-amdgpu-pro-radeon1_2.4.70-379184_amd64.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libdrm-amdgpu-pro-utils_2.4.70-379184_amd64.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libdrm2-amdgpu-pro_2.4.70-379184_amd64.deb
	#move_libdir "${pkgdir}/opt/amdgpu-pro" "usr"
	#move_libdir "${pkgdir}/opt/amdgpu-pro/lib/x86_64-linux-gnu"
	move_libdir "${pkgdir}/lib"

}


package_amdgpu-pro-libgl () {
	pkgdesc="The AMDGPU Pro libgl library symlinks"
	arch=('x86_64')
	provides=('libgl')
	conflicts=('libgl')
	depends=(amdgpu-pro)

	#move_libdir "${pkgdir}/opt/amdgpu-pro" "usr"
	#move_libdir "${pkgdir}/opt/amdgpu-pro/lib/x86_64-linux-gnu"
	move_libdir "${pkgdir}/lib"

	# extra_commands:
	mkdir -p "${pkgdir}"/usr/lib
	cd "${pkgdir}"/usr/lib
	ln -s /opt/amdgpu-pro/lib/x86_64-linux-gnu/libGL.so.1.2   libGL.so.1.2
	ln -s /opt/amdgpu-pro/lib/x86_64-linux-gnu/libEGL.so.1    libEGL.so.1
	ln -s /opt/amdgpu-pro/lib/x86_64-linux-gnu/libGLESv2.so.2 libGLESv2.so.2
	ln -s libGL.so.1.2   libGL.so.1
	ln -s libGL.so.1.2   libGL.so
	ln -s libEGL.so.1    libEGL.so
	ln -s libGLESv2.so   libGLESv2.so
}


package_amdgpu-pro-opencl () {
	pkgdesc="The AMDGPU Pro OpenCL implementation"
	arch=('x86_64')
	provides=('opencl-driver')
	depends=()

	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./clinfo-amdgpu-pro_16.60-379184_amd64.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libopencl1-amdgpu-pro_16.60-379184_amd64.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./opencl-amdgpu-pro-icd_16.60-379184_amd64.deb
	#move_libdir "${pkgdir}/opt/amdgpu-pro" "usr"
	#move_libdir "${pkgdir}/opt/amdgpu-pro/lib/x86_64-linux-gnu"
	move_libdir "${pkgdir}/lib"

}


package_amdgpu-pro-vdpau () {
	pkgdesc="The AMDGPU Pro VDPAU driver"
	arch=('x86_64')
	depends=('amdgpu-pro-libdrm=16.60.379184-0' 'libvdpau>=1.1' 'libxcb' 'libxcb>=1.8' 'ncurses>=6' 'openssl>=1.0.0' 'zlib>=1.2.0')

	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libvdpau-amdgpu-pro_12.0.3-379184_amd64.deb
	#move_libdir "${pkgdir}/opt/amdgpu-pro" "usr"
	#move_libdir "${pkgdir}/opt/amdgpu-pro/lib/x86_64-linux-gnu"
	move_libdir "${pkgdir}/lib"

}


package_amdgpu-pro-vulkan () {
	pkgdesc="The AMDGPU Pro Vulkan driver"
	arch=('x86_64')
	depends=('amdgpu-pro-libdrm=16.60.379184-0')

	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./vulkan-amdgpu-pro_16.60-379184_amd64.deb
	#move_libdir "${pkgdir}/opt/amdgpu-pro" "usr"
	#move_libdir "${pkgdir}/opt/amdgpu-pro/lib/x86_64-linux-gnu"
	move_libdir "${pkgdir}/lib"

	# extra_commands:
	#sed -i 's@/usr/lib/x86_64-linux-gnu/@/usr/lib/@' ${pkgdir}/etc/vulkan/icd.d/amd_icd64.json
}


package_lib32-amdgpu-pro () {
	pkgdesc="Meta package to install amdgpu Pro components. (32bit libraries)"
	arch=('x86_64')
	depends=('amdgpu-pro-dkms=16.60.379184-0' 'amdgpu-pro-libdrm=16.60.379184-0' 'amdgpu-pro-opencl=16.60.379184-0' 'amdgpu-pro-vdpau=16.60.379184-0' 'amdgpu-pro-vulkan=16.60.379184-0' 'amdgpu-pro=16.60.379184-0' 'lib32-glib2>=2.37.3' 'lib32-gst-plugins-base>=1.6.0' 'lib32-gstreamer>=1.0.0' 'lib32-libomxil-bellagio' 'lib32-libx11' 'lib32-libx11>=1.4.99.1' 'lib32-libxcb' 'lib32-libxcb>=1.8' 'lib32-libxcb>=1.9.2' 'lib32-libxdamage>=1.1' 'lib32-libxext' 'lib32-libxfixes' 'lib32-libxshmfence' 'lib32-libxxf86vm' 'lib32-ncurses>=6' 'lib32-openssl>=1.0.0' 'lib32-zlib>=1.2.0' 'xf86-video-amdgpu-pro=16.60.379184-0')

	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./amdgpu-pro_16.60-379184_i386.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./gst-omx-amdgpu-pro_1.0.0.1-379184_i386.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libegl1-amdgpu-pro_16.60-379184_i386.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libgbm1-amdgpu-pro_16.60-379184_i386.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libgbm1-amdgpu-pro-dev_16.60-379184_i386.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libgl1-amdgpu-pro-dri_16.60-379184_i386.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libgl1-amdgpu-pro-ext_16.60-379184_i386.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libgl1-amdgpu-pro-glx_16.60-379184_i386.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libglamor-amdgpu-pro-dev_1.18.3-379184_i386.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libgles2-amdgpu-pro_16.60-379184_i386.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./mesa-amdgpu-pro-omx-drivers_12.0.3-379184_i386.deb
	#move_libdir "${pkgdir}/opt/amdgpu-pro" "usr"
	#move_libdir "${pkgdir}/opt/amdgpu-pro/lib/i386-linux-gnu" "usr/lib32"
	move_libdir "${pkgdir}/lib" "usr/lib32"

	# extra_commands:
	rm -rf "${pkgdir}"/etc
	#mkdir -p "${pkgdir}"/usr/lib32/amdgpu-pro
	#mv "${pkgdir}"/usr/lib32/libGLESv2.so* "${pkgdir}"/usr/lib32/amdgpu-pro/
	#mv "${pkgdir}"/usr/lib32/libGL.so* "${pkgdir}"/usr/lib32/amdgpu-pro/
	#mv "${pkgdir}"/usr/lib32/libEGL.so* "${pkgdir}"/usr/lib32/amdgpu-pro/

	# lib32 cleanup
	rm -rf "${pkgdir}"/usr/{bin,lib,include,share} "${pkgdir}/var" "${pkgdir}"/opt/amdgpu-pro/{bin,include,share}
	rm -rf "${pkgdir}"/opt/amdgpu-pro/lib/xorg/modules/extensions/

}


package_lib32-amdgpu-pro-libdrm () {
	pkgdesc="The AMDGPU Pro userspace interface to kernel DRM services (32bit libraries)"
	arch=('x86_64')
	depends=('amdgpu-pro-libdrm=16.60.379184-0')

	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libdrm-amdgpu-pro-amdgpu1_2.4.70-379184_i386.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libdrm-amdgpu-pro-dev_2.4.70-379184_i386.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libdrm-amdgpu-pro-radeon1_2.4.70-379184_i386.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libdrm2-amdgpu-pro_2.4.70-379184_i386.deb
	#move_libdir "${pkgdir}/opt/amdgpu-pro" "usr"
	#move_libdir "${pkgdir}/opt/amdgpu-pro/lib/i386-linux-gnu" "usr/lib32"
	move_libdir "${pkgdir}/lib" "usr/lib32"


	# lib32 cleanup
	rm -rf "${pkgdir}"/usr/{bin,lib,include,share} "${pkgdir}/var" "${pkgdir}"/opt/amdgpu-pro/{bin,include,share}
	rm -rf "${pkgdir}"/opt/amdgpu-pro/lib/xorg/modules/extensions/

}


package_lib32-amdgpu-pro-libgl () {
	pkgdesc="The AMDGPU Pro libgl library symlinks (32bit libraries)"
	arch=('x86_64')
	provides=('lib32-libgl')
	conflicts=('lib32-libgl')
	depends=(lib32-amdgpu-pro)

	#move_libdir "${pkgdir}/opt/amdgpu-pro" "usr"
	#move_libdir "${pkgdir}/opt/amdgpu-pro/lib/i386-linux-gnu" "usr/lib32"
	move_libdir "${pkgdir}/lib" "usr/lib32"

	# extra_commands:
	mkdir -p "${pkgdir}"/usr/lib32
	cd "${pkgdir}"/usr/lib32
	ln -s /opt/amdgpu-pro/lib/i386-linux-gnu/libGL.so.1.2   libGL.so.1.2
	ln -s /opt/amdgpu-pro/lib/i386-linux-gnu/libEGL.so.1    libEGL.so.1
	ln -s /opt/amdgpu-pro/lib/i386-linux-gnu/libGLESv2.so.2 libGLESv2.so.2
	ln -s libGL.so.1.2   libGL.so.1
	ln -s libGL.so.1.2   libGL.so
	ln -s libEGL.so.1    libEGL.so
	ln -s libGLESv2.so   libGLESv2.so

	# lib32 cleanup
	rm -rf "${pkgdir}"/usr/{bin,lib,include,share} "${pkgdir}/var" "${pkgdir}"/opt/amdgpu-pro/{bin,include,share}
	rm -rf "${pkgdir}"/opt/amdgpu-pro/lib/xorg/modules/extensions/

}


package_lib32-amdgpu-pro-opencl () {
	pkgdesc="The AMDGPU Pro OpenCL implementation"
	arch=('x86_64')
	provides=('lib32-libcl')
	conflicts=('lib32-libcl')
	depends=()

	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libopencl1-amdgpu-pro_16.60-379184_i386.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./opencl-amdgpu-pro-icd_16.60-379184_i386.deb
	#move_libdir "${pkgdir}/opt/amdgpu-pro" "usr"
	#move_libdir "${pkgdir}/opt/amdgpu-pro/lib/i386-linux-gnu" "usr/lib32"
	move_libdir "${pkgdir}/lib" "usr/lib32"


	# lib32 cleanup
	rm -rf "${pkgdir}"/usr/{bin,lib,include,share} "${pkgdir}/var" "${pkgdir}"/opt/amdgpu-pro/{bin,include,share}
	rm -rf "${pkgdir}"/opt/amdgpu-pro/lib/xorg/modules/extensions/

}


package_lib32-amdgpu-pro-vdpau () {
	pkgdesc="The AMDGPU Pro VDPAU driver (32bit libraries)"
	arch=('x86_64')
	depends=('amdgpu-pro-libdrm=16.60.379184-0' 'lib32-libvdpau>=1.1' 'lib32-libxcb' 'lib32-libxcb>=1.8' 'lib32-ncurses>=6' 'lib32-openssl>=1.0.0' 'lib32-zlib>=1.2.0')

	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./libvdpau-amdgpu-pro_12.0.3-379184_i386.deb
	#move_libdir "${pkgdir}/opt/amdgpu-pro" "usr"
	#move_libdir "${pkgdir}/opt/amdgpu-pro/lib/i386-linux-gnu" "usr/lib32"
	move_libdir "${pkgdir}/lib" "usr/lib32"


	# lib32 cleanup
	rm -rf "${pkgdir}"/usr/{bin,lib,include,share} "${pkgdir}/var" "${pkgdir}"/opt/amdgpu-pro/{bin,include,share}
	rm -rf "${pkgdir}"/opt/amdgpu-pro/lib/xorg/modules/extensions/

}


package_lib32-amdgpu-pro-vulkan () {
	pkgdesc="The AMDGPU Pro Vulkan driver (32bit libraries)"
	arch=('x86_64')
	depends=('amdgpu-pro-libdrm=16.60.379184-0')

	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./vulkan-amdgpu-pro_16.60-379184_i386.deb
	#move_libdir "${pkgdir}/opt/amdgpu-pro" "usr"
	#move_libdir "${pkgdir}/opt/amdgpu-pro/lib/i386-linux-gnu" "usr/lib32"
	move_libdir "${pkgdir}/lib" "usr/lib32"

	# extra_commands:
	#sed -i 's@/usr/lib/i386-linux-gnu/@/usr/lib32/@' ${pkgdir}/etc/vulkan/icd.d/amd_icd32.json

	# lib32 cleanup
	rm -rf "${pkgdir}"/usr/{bin,lib,include,share} "${pkgdir}/var" "${pkgdir}"/opt/amdgpu-pro/{bin,include,share}
	rm -rf "${pkgdir}"/opt/amdgpu-pro/lib/xorg/modules/extensions/

}


package_xf86-video-amdgpu-pro () {
	pkgdesc="The AMDGPU Pro X.org video driver"
	arch=('x86_64')
	provides=('xf86-video-amdgpu')
	conflicts=('xf86-video-amdgpu' 'xorg-server<1.18.0' 'X-ABI-VIDEODRV_VERSION<20' 'X-ABI-VIDEODRV_VERSION>=24')
	groups=('xorg-driversxorg')
	depends=('amdgpu-pro-libdrm=16.60.379184-0' 'amdgpu-pro=16.60.379184-0' 'libepoxy>=1.0' 'libsystemd>=183')

	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./xserver-xorg-video-amdgpu-pro_1.2.99-379184_amd64.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./xserver-xorg-video-glamoregl-amdgpu-pro_1.18.3-379184_amd64.deb
	extract_deb "${srcdir}"/amdgpu-pro-16.60-379184/./xserver-xorg-video-modesetting-amdgpu-pro_1.18.3-379184_amd64.deb
	#move_libdir "${pkgdir}/opt/amdgpu-pro" "usr"
	#move_libdir "${pkgdir}/opt/amdgpu-pro/lib/x86_64-linux-gnu"
	move_libdir "${pkgdir}/lib"

	# extra_commands:
	#mv ${pkgdir}/usr/lib/amdgpu-pro/1.18/ ${pkgdir}/usr/lib/xorg
	#rm -rf ${pkgdir}/usr/lib/amdgpu-pro/1.*
}

