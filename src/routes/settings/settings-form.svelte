<script lang="ts">
	import * as Form from '$lib/components/ui/form';
	import * as Card from '$lib/components/ui/card';

	import { formSchema } from './schema';
	import type { SuperValidated } from 'sveltekit-superforms';
	export let form: SuperValidated<any>;
</script>

<Card.Root>
	<Form.Root method="POST" {form} schema={formSchema} let:config>
		<Card.Header>
			<Card.Title>Register form</Card.Title>
			<Card.Description>Register user</Card.Description>
		</Card.Header>
		<Card.Content>
			<Form.Field {config} name="username">
				<Form.Item>
					<Form.Label>Username</Form.Label>
					<Form.Input />
					<Form.Description>This is your public display name.</Form.Description>
					<Form.Validation />
				</Form.Item>
			</Form.Field>
			<Form.Field {config} name="password">
				<Form.Item>
					<Form.Label>Password</Form.Label>
					<Form.Input type="password" />
					<Form.Description>This is your password.</Form.Description>
					<Form.Validation />
				</Form.Item>
			</Form.Field>
		</Card.Content>
		<Card.Footer>
			<Form.Button>Submit</Form.Button>
		</Card.Footer>
	</Form.Root>
</Card.Root>
