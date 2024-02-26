## wp list table
```php
protected function process_bulk_action() {
		global $wpdb;

		/*
		$delete_nonce = isset( $_REQUEST['delete_nonce'] ) ? $_REQUEST['delete_nonce'] : '';

		if ( ! $this->current_action() ) {
			return;
		}

		if ( 'delete' === $this->current_action() ) {

			if ( ! wp_verify_nonce( $delete_nonce, 'deletentry' ) ) {
				wp_die( 'No action taken2' );
				exit();
			}

			if ( is_array( $_REQUEST['id'] ) ) {
				print_r( $_REQUEST['id'] );
			}
			// $ids = $this->get_user_selected_records();
			$ids = isset( $_REQUEST['id'] ) ? $_REQUEST['id'] : array();
			if ( is_array( $ids ) ) {
				$ids = implode( ',', $ids );
			}

			if ( ! empty( $ids ) ) {
				$wpdb->query( "DELETE FROM $table_name WHERE id IN($ids)" );
			}
		} */
	}
```
