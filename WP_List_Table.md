#### wp_list_table github
https://github.com/Veraxus/wp-list-table-example/blob/master/includes/class-tt-example-list-table.php

### wp list table
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

// PS to add links to the column create a function with name column_(and the name of the column)
	protected function column_id( $item ) {

		/*
		$page         = wp_unslash( $_REQUEST['page'] );
		$delete_nonce = wp_create_nonce( 'deletentry' );

		// Build edit row action.
		$edit_query_args = array(
			'page'   => $page,
			'action' => 'edit',
			'id'     => $item['id'],

		);

		$actions['edit'] = sprintf(
			'<a href="%1$s">%2$s</a>',
			esc_url( wp_nonce_url( add_query_arg( $edit_query_args, 'admin.php' ), 'editentry_' . $item['id'] ) ),
			_x( 'Edit', 'List table row action', 'wp-list-adas' )
		);

		// Build delete row action.
		$delete_query_args = array(
			'page'   => $page,
			'action' => 'delete',
			'id'     => $item['id'],
		);

		$actions['delete'] = sprintf(
			'<a href="%1$s&delete_nonce=%2$s">%3$s</a>',
			esc_url( add_query_arg( $delete_query_args, 'admin.php' ) ),
			esc_attr( $delete_nonce ),
			_x( 'Delete', 'List table row action', 'wp-list-adas' )
		);

		// Return the page_id contents.
		return sprintf(
			'%2$s <span style="color:silver;">entry</span>%3$s',
			$item['page_id'],
			$item['id'],
			$this->row_actions( $actions )
		);*/
	}


```
