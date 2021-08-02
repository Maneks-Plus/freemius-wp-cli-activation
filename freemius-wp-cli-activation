<?php
/*
Plugin Name: Freemius License Activation
Plugin URI: https://github.com/Maneks-Plus/freemius-wp-cli-activation
GitHub Plugin URI: https://github.com/Maneks-Plus/freemius-wp-cli-activation
Version: 1.0.0
Author: maneks-plus

Based off of this repository:
https://github.com/squarecandy/freemius-auto-activation
*/

add_action( 'plugins_loaded', 'maneks_freemius_activation' );
function maneks_freemius_activation() {

	if ( ! class_exists( 'Freemius_License_Activator' ) ) {
		require_once plugin_dir_path( __FILE__ ) . 'class-freemius-license-activator.php';
	}

	if ( defined( 'FS_SHORTCODES' ) && ! empty( FS_SHORTCODES ) ) :
		if ( ! is_array( FS_SHORTCODES ) ) {
			$fs_shortcodes = array( FS_SHORTCODES );
		} else {
			$fs_shortcodes = FS_SHORTCODES;
		}
		foreach ( $fs_shortcodes as $fs_shortcode ) :
			if ( defined( 'WP__' . strtoupper( $fs_shortcode ) . '__LICENSE_KEY' ) ) {
				$fs_license_activator = new Freemius_License_Activator( $fs_shortcode );
			}
		endforeach;
	endif;
}
